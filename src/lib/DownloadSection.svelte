<script>
    import googleLogo from '../assets/images/logo-chrome.svg'
    import firefoxLogo from '../assets/images/logo-firefox.svg'
    import operaLogo from '../assets/images/logo-opera.svg'
    import dots from '../assets/images/bg-dots.svg'
    import DownloadButton from './components/DownloadButton.svelte';

    const extensions = [
        {
            name: 'Chrome',
            version: '62',
            logo: googleLogo
        },
        {
            name: 'Firefox',
            version: '55',
            logo: firefoxLogo
        },
        {
            name: 'Opera',
            version: '46',
            logo: operaLogo
        }
    ];
</script>

<section class=" mb-90">
    <div class="container">
        <article class=" mb-24">
            <div class=" max-w-full md:max-w-[600px] mx-auto">
                <h2 class=" text-center text-3xl text-blue-950 font-[600] mb-4 md:mb-6 ">
                    Download the extension
                </h2>
                <p class="text-center text-gray-500">
                    We’ve got more browsers in the pipeline. Please do let us know if you’ve 
                    got a favourite you’d like us to prioritize.
                </p>
            </div>
        </article>
        <section class=" md:flex gap-3  md:gap-6 justify-center items-center ">
            {#each extensions as extension, i }
                <article class=" max-w-full md:w-[280px] shadow-[0_12px_24px_rgba(0,0,0,0.1)]
                    {i === 1 ? `md:transform translate-y-[100px]` : ""}
                    {i === 2 ? `md:transform translate-y-[200px]` : ""}
                ">
                    <div class=" py-12">
                        <figure class=" max-w-full mb-6">
                            <img class="mx-auto" src={extension.logo} alt={extension.name}>
                        </figure>
                        <h3 class="font-[600] text-blue-950 text-[1.3em] text-center mb-3 ">
                            Add to { extension.name }
                        </h3>
                        <p class=" text-center text-gray-500 font-[400] ">
                            Minimum version { extension.version }
                        </p>
                    </div>
                    <img class=" max-w-full mx-auto" src={dots} alt="" aria-hidden="true">
                    <div class=" p-4 pt-6 flex items-center justify-center">
                        <DownloadButton content={"Add & Install Extension"} />
                    </div>
                </article>
            {/each}
        </section>
    </div>
</section>



