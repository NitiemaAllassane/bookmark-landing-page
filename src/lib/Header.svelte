<script>
    import Logo from "./components/Logo.svelte";
    import Navigation from "./components/Navigation.svelte";
    import LoginButton from "./components/LoginButton.svelte";

    import MenuButton from "./components/MenuButton.svelte";
</script>


<header class="py-8 mb-16">
    <div class="container flex justify-between items-center">
        <Logo />
        <div class="hidden md:flex items-center gap-8">
            <Navigation />
            <LoginButton />
        </div>
        <MenuButton />
    </div>
</header>