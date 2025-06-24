<script>
    let { content } = $props()
</script>


<a
    class="inline-block w-full py-2 px-4 bg-blue-600 rounded-sm text-center sm:text-[1em] text-[0.8em] text-white border-2
    transition duration-200 tracking-[1px] border-blue-600 shadow-[0_5px_10px_rgba(0,0,0,0.2)]
    hover:bg-transparent hover:text-blue-600" 

    href="/"
>
    {content}
</a>