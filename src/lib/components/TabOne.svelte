<script>
    import { fly } from 'svelte/transition';
    import tabImage from '../../assets/images/illustration-features-tab-1.svg'
    import MoreButton from './MoreButton.svelte';
</script>


<article class="flex flex-col items-center gap-12 md:gap-24 md:flex-row">
    <figure in:fly={{y: -100, duration: 400}} class=" mb-4 md:mb-0">
        <img src={ tabImage } alt="" aria-hidden="true">
    </figure>
    <div class="max-w-full md:w-1/2">
        <h2 in:fly={{y: 80, duration: 500, delay:200}} class=" text-center font-[600] text-blue-950 text-3xl mb-4 md:mb-6 md:text-start ">Bookmark in one click</h2>
        <p in:fly={{y: 80, duration: 500, delay:300}} class=" text-center text-gray-500 font-[400] md:text-start mb-6 ">
            Organize your bookmarks however you like. Our simple drag-and-drop interface 
            gives you complete control over how you manage your favourite sites.
        </p>
        <MoreButton hidden={true} />
    </div>
</article>