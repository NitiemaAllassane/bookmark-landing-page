<script>
    import facebookIcon from '../assets/images/icon-facebook.svg';
    import twiterIcon from '../assets/images/icon-twitter.svg';
  import FooterLogo from './components/FooterLogo.svelte';
  import FooterNav from './components/FooterNav.svelte';
    import Logo from "./components/Logo.svelte";
    import Navigation from "./components/Navigation.svelte";

</script>


<footer class="py-12 bg-blue-950">
    <div class="container flex flex-col gap-16 md:gap-0 md:flex-row justify-between items-center">
        <div class=" flex flex-col md:flex-row items-center justify-center gap-11">
            <FooterLogo />
            <FooterNav />
        </div>
        <div class=" flex items-center gap-8 md:gap-4">
            <a href="/" aria-label="Facebook">
                <img src={facebookIcon} alt="facebook icon">
            </a>
            <a href="/" aria-label="Twiter">
                <img src={twiterIcon} alt="Twiter icon">
            </a>
        </div>
    </div>
</footer>