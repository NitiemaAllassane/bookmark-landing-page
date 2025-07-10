<script>
    import CloseButton from "./CloseButton.svelte";
    import FooterLogo from "./FooterLogo.svelte";

    import facebookIcon from '../../assets/images/icon-facebook.svg';
    import twiterIcon from '../../assets/images/icon-twitter.svg';

    import { slide } from "svelte/transition";
    import { mobileNav } from "../states.svelte";

    let navLinks = [
        {content: "Features", id: 0},
        {content: "Pricing", id: 1},
        {content: "Contact", id: 2}
    ]
</script>


<!-- svelte-ignore a11y_no_redundant_roles -->
<nav 
    class="fixed top-0 left-0 w-full h-full opacity-90 bg-blue-950 z-50 md:hidden" 
    in:slide={{duration: 500}}
    out:slide={{duration: 300}}
    id="mobile_navigation"
    role="navigation"
>
    <div class="container">
        <div class="mb-[60%]">
            <header class=" flex justify-between items-center py-8">
                <FooterLogo />
                <CloseButton onButtonClick={mobileNav.isMobileOpened = false} />
            </header>
            <ul class=" mb-6">
                {#each navLinks as link (link.id) }
                    <li 
                        class=" py-4 border-t border-gray-500 flex items-center justify-center
                        {link.id === 2 ? `border-b`: ''} "
                    >
                        <a href="/" class=" text-2xl text-white font-normal tracking-[3px] ">
                            {link.content}
                        </a>
                    </li>
                {/each}
            </ul>
            <a href="/" class=" inline-block w-full py-2.5 text-center border-2 border-white text-2xl font-semibold text-white " >
                Login
            </a>
        </div>

        <div class="flex items-center justify-center gap-8">
            <a href="/" aria-label="Facebook">
                <img src={facebookIcon} alt="facebook icon">
            </a>
            <a href="/" aria-label="Twiter">
                <img src={twiterIcon} alt="Twiter icon">
            </a>
        </div>
    </div>
</nav>
