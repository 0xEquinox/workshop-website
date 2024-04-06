<script>
    import NavBar from "../componenets/NavBar.svelte";
    import Heading from "../componenets/Heading.svelte";
    import {onMount} from "svelte";
    import Footer from "../componenets/Footer.svelte";

    const aboutSections = ["Who", "About", "Details"];
    let activeInfoSection = 1;

    let activeShowcaseSection = 0;

    let infoSectionEl;
    let showcaseSectionEl;

    const infoScroll = (e) => {
        const w = e.target.scrollWidth / 3;
        const sl = e.target.scrollLeft;

        activeInfoSection = Math.floor((sl + w * 0.5) / w);
    };

    const infoScrollTo = (change) => {
        const sectionWidth = infoSectionEl.scrollWidth / 3;
        const sectionIndex = (activeInfoSection + change + 3) % 3;

        infoSectionEl.scrollLeft = sectionWidth * sectionIndex;
    };

    const showcaseScroll = (e) => {
        const w = e.target.clientWidth;
        const sl = e.target.scrollLeft;

        activeShowcaseSection = Math.floor((sl + w * 0.5) / w);
    };

    const showcaseScrollTo = (index) => {
        const itemWidth = showcaseSectionEl.clientWidth;

        showcaseSectionEl.scrollLeft = itemWidth * index;
    };

    onMount(() => {
        infoSectionEl.scrollLeft = infoSectionEl.scrollWidth / 3;
    });
</script>

<div class="b relative flex min-h-screen justify-center bg-violet-100 text-gray-700" id="home">
    <div class="min-w-6xl z-50 flex w-full max-w-6xl flex-grow flex-col bg-blue-100 shadow-[0_20px_25px_-5px_rgb(0_0_0_/_0.2),_0_8px_10px_-6px_rgb(0_0_0_/_0.2)]">
        <NavBar />
        <div class="h-screen flex flex-col justify-center">
            <div class="mt-16 px-6 font-poppins text-gray-700 bg-blue-100 flex items-center mb-64">
                <div>
                    <h1 class="mb-2 text-left text-5xl font-bold leading-[1.2] sm:mb-6 sm:text-8xl">
                        Electronics<br /> Workshop
                    </h1>
                    <div class="mb-8 flex sm:mb-12 sm:text-2xl">
                        <div class="mr-2 flex items-center">
                            <p class="flex font-bold"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                <path fill-rule="evenodd" d="m11.54 22.351.07.04.028.016a.76.76 0 0 0 .723 0l.028-.015.071-.041a16.975 16.975 0 0 0 1.144-.742 19.58 19.58 0 0 0 2.683-2.282c1.944-1.99 3.963-4.98 3.963-8.827a8.25 8.25 0 0 0-16.5 0c0 3.846 2.02 6.837 3.963 8.827a19.58 19.58 0 0 0 2.682 2.282 16.975 16.975 0 0 0 1.145.742ZM12 13.5a3 3 0 1 0 0-6 3 3 0 0 0 0 6Z" clip-rule="evenodd" />
                            </svg>
                                Redmond, WA</p>
                        </div>
                        <div class="flex items-center">
                            <p class="flex font-bold"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                <path d="M12.75 12.75a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM7.5 15.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5ZM8.25 17.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM9.75 15.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5ZM10.5 17.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM12 15.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5ZM12.75 17.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM14.25 15.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5ZM15 17.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM16.5 15.75a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5ZM15 12.75a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0ZM16.5 13.5a.75.75 0 1 0 0-1.5.75.75 0 0 0 0 1.5Z" />
                                <path fill-rule="evenodd" d="M6.75 2.25A.75.75 0 0 1 7.5 3v1.5h9V3A.75.75 0 0 1 18 3v1.5h.75a3 3 0 0 1 3 3v11.25a3 3 0 0 1-3 3H5.25a3 3 0 0 1-3-3V7.5a3 3 0 0 1 3-3H6V3a.75.75 0 0 1 .75-.75Zm13.5 9a1.5 1.5 0 0 0-1.5-1.5H5.25a1.5 1.5 0 0 0-1.5 1.5v7.5a1.5 1.5 0 0 0 1.5 1.5h13.5a1.5 1.5 0 0 0 1.5-1.5v-7.5Z" clip-rule="evenodd" />
                            </svg>
                                April 23rd, 2023</p>
                        </div>
                    </div>
                    <button  onclick="window.location.href='https://forms.gle/ottDRT8QXbhQqCE5A';" class="bg-blue-500 text-white text-2xl font-bold rounded-lg p-2">
                        Register
                    </button>
                </div>
            </div>
            <div class="mb-12 bg-green-200">
                <div class="flex items-baseline justify-center md:hidden" role="tablist">
                    <h2
                            class="flex-1 select-none text-right font-poppins text-lg font-bold text-gray-700"
                            role="tab"
                            on:click={() => infoScrollTo(-1)}
                    >
                        {aboutSections[(activeInfoSection + 3 - 1) % 3]}
                    </h2>
                    <Heading role="tab">
                        {aboutSections[(activeInfoSection + 3) % 3]}
                    </Heading>
                    <h2
                            class="flex-1 select-none text-left font-poppins text-lg font-bold text-gray-700"
                            role="tab"
                            on:click={() => infoScrollTo(1)}
                    >
                        {aboutSections[(activeInfoSection + 3 + 1) % 3]}
                    </h2>
                </div>

                <div
                        class="flex w-full snap-x snap-mandatory overflow-auto scroll-smooth md:overflow-hidden"
                        on:scroll={infoScroll}
                        bind:this={infoSectionEl}
                >
                    <div class="flex-1 snap-center snap-always" role="tabpanel">
                        <div class="hidden justify-center md:flex">
                            <Heading>Who</Heading>
                        </div>
                        <p class="w-screen px-2 py-4 font-semibold md:w-auto">
                            I am a senior at the Bellevue International school, and I've been working on this project for my senior project for the last couple months, and I'm excited to share what I've learned!
                        </p>
                    </div>

                    <div class="flex-1 snap-center snap-always" role="tabpanel">
                        <div class="hidden justify-center md:flex">
                            <Heading>About</Heading>
                        </div>
                        <p class="w-screen px-2 py-4 font-semibold md:w-auto">
                            During the electronics workshop, attendees will learn about basic electronics and soldering by building a mp3 player kit that I've designed over the last few months. This is a great opportunity to learn about electronics and go home with a new mp3 player!
                        </p>
                    </div>

                    <div class="flex-1 snap-center snap-always" role="tabpanel">
                        <div class="hidden justify-center md:flex">
                            <Heading>Details</Heading>
                        </div>
                        <p class="w-screen px-2 py-4 font-semibold md:w-auto">
                            When: April 23rd <br />
                            Where: Redmond Library (15990 NE 85th Street
                            Redmond, WA 98052)
                            <br />
                            Who: Any high school student <br />
                            Why: because it's fun!
                        </p>
                    </div>
                </div>
            </div>
        </div>
        <Footer />
    </div>
</div>

