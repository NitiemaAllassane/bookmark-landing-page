<script>
    import CloseButton from "./CloseButton.svelte";
    import FooterLogo from "./FooterLogo.svelte";
    import { slide } from "svelte/transition";

    import { mobileNav } from "../states.svelte";
    import { bounceOut, elasticOut, quadOut } from "svelte/easing";

    let navLinks = [
        {content: "Features", id: 0},
        {content: "Pricing", id: 1},
        {content: "Contact", id: 2}
    ]
</script>


<nav 
    class="fixed top-0 left-0 w-full h-full opacity-90 bg-blue-950 z-50 md:hidden" 
    in:slide={{duration: 500, easing: bounceOut}}
    out:slide={{duration: 300}}
>
    <div class="container">
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
</nav>
