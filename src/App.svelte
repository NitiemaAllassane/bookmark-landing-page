<script>
    import DownloadSection from "./lib/DownloadSection.svelte";
    import FaqSection from "./lib/FaqSection.svelte";
    import Features from "./lib/Features.svelte";
    import Footer from "./lib/Footer.svelte";
    import Header from "./lib/Header.svelte";
    import Hero from "./lib/Hero.svelte";
    import Newsletter from "./lib/Newsletter.svelte";
</script>


<main>
    <Header />
    <Hero />
    <Features />
    <DownloadSection />
    <FaqSection />
    <Newsletter />
    <Footer />
    <small class=" inline-block p-2 text-center w-full bg-white text-blue-950">
        Challenge by 
        <a class=" text-blue-600 underline" href="https://www.frontendmentor.io/home" target="_blank">
            Frontend Mentor
        </a>.
        Coded by <a class="text-blue-600 underline" href="https://www.frontendmentor.io/profile/NitiemaAllassane" target="_blank">Nitiema Allassane</a>.
    </small>
</main>