<script>
    import heroImage from '../assets/images/illustration-hero.svg'
</script>



<section class=" mb-24">
    <div class="container flex flex-col-reverse items-center md:flex-row gap-12">
       <article>
            <h1 class=" text-4xl leading-[1.2] md:text-5xl text-center md:text-start text-blue-950 font-[600] mb-6">A Simple Bookmark Manager</h1>
            <p class=" text-gray-500 text-center md:text-start font-[400] mb-8 ">
                A clean and simple interface to organize your favourite websites. Open a new 
                browser tab and see your sites load instantly. Try it for free.
            </p>
            <div class="flex items-center gap-5 justify-center md:justify-start ">
                <a
                    class="inline-block py-2 px-4 bg-blue-600 rounded-sm text-center sm:text-[1em] text-[0.8em] text-white border-2
                    transition duration-200 tracking-[1px] border-blue-600 shadow-[0_5px_10px_rgba(0,0,0,0.2)]
                    hover:bg-transparent hover:text-blue-600" 

                    href="/"
                >
                    Get it on Chrome
                </a>
                <a
                    class="inline-block py-2 px-4 bg-gray-50 rounded-sm text-center text-[0.8em] sm:text-[1em] text-blue-950 border-2
                    transition duration-200 tracking-[1px] border-gray-50 shadow-[0_5px_10px_rgba(0,0,0,0.2)]
                    hover:bg-transparent hover:text-blue-950 hover:border-blue-950" 

                    href="/"
                >
                    Get it on Firefox
                </a>
            </div>
       </article>

       <figure 
            class="md:w-full md:h-full"
        >
            <img class=" w-full h-full object-cover" src={heroImage} alt="A tablet Illustration">
       </figure>
    </div>
</section>