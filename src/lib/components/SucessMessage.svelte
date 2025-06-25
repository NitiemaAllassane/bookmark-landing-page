<script>
    import { CheckIcon } from "lucide-svelte";
    import { fly, fade } from "svelte/transition";


</script>

<div 
    class="w-full h-full fixed top-0 left-0 bg-[rgba(0,0,0,0.2)] "
    transition:fade={{duration: 200}}
>
    <div 
        class=" flex  rounded-sm gap-3 bg-green-600 text-white p-3 
        absolute top-8 left-1/2 md:top-auto md:left-auto md:bottom-7 md:right-0 transform translate-x-[-50%] max-w-full "
        transition:fly={{y: 80, duration: 200}}
    >
        <CheckIcon class="text-white" size="28" strokeWidth="2.5" />
        <span>Thanks for subscribing! You’ll hear from us soon.</span>
    </div>
</div>