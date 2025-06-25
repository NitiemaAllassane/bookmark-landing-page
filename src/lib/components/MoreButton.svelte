<script>
    import { fly } from "svelte/transition";
    let { hidden } = $props();
</script>

<a 
    in:fly={{y: 80, duration: 500, delay:400}} href="/" 
    class=" {hidden ? 'hidden' : 'inline-block'} md:inline-block py-2.5 px-5 bg-blue-600 text-white rounded-sm"
>
    More Info
</a>