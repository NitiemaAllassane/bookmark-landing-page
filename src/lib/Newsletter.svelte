<script>
    import errorIcon from '../assets/images/icon-error.svg';
    import ContactButton from './components/ContactButton.svelte';
  import SucessMessage from './components/SucessMessage.svelte';

    let hasError = $state(false);
    let success = $state(false);
    let userEmail = $state("");

    function handleFormSubmission(e) {
        e.preventDefault();

        if (!userEmail) return;

        if (!isEmailValid(userEmail)) {
            hasError = true;
            return;
        }

        userEmail = "";
        hasError = false;
        success = true;
        
    }


    function isEmailValid(email) {
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(email);
    }

    $effect(() => {
        if (success) {
            const id = setTimeout(() => {
                success = false;
            }, 2000);
            return () => clearTimeout(id);
        }
    });

</script>


<section class=" bg-blue-600 h-[40vh] flex justify-center items-center py-44 ">
    <div class="container">
        <article>
            <div class=" max-w-full md:max-w-[600px] mx-auto">
                <p class=" text-center text-white mb-4 tracking-[2px] ">35,000+ already joined</p>
                <h2 class=" text-center text-2xl md:text-3xl text-white font-[600] mb-4 md:mb-6 ">
                    Stay up-to-date with what we’re doing
                </h2>
                <form 
                    class="flex flex-col items-center md:flex-row gap-4 md:gap-6 w-fit mx-auto"
                    onsubmit={handleFormSubmission}
                >
                   <div class="relative w-full md:w-auto">
                         <div 
                            class=" flex items-center bg-white p-3 gap-3 w-full md:w-auto rounded-sm relative
                            {hasError ? `outline-red-400 outline-3 focus-within:outline-red-400 ` : `focus-within:outline-3 focus-within:outline-blue-950`}
                            "
                            aria-label="Enter your email"
                        >
                            <input 
                                type="email" 
                                name="email" 
                                id="email" 
                                placeholder="Enter your email address"
                                class=" w-full h-full outline-none"
                                bind:value={userEmail}
                                required
                            >
                            {#if hasError}
                                <img src={errorIcon} alt="Error Icon">
                            {/if}
                        </div>
                        {#if hasError}
                            <small class="absolute py-1 px-2 italic left-0 bottom-full md:bottom-auto md:top-full w-full rounded-sm bg-red-400 text-white">
                                Whoops, make sure it's an email
			                </small>
                        {/if}
                   </div>
                    <ContactButton />
                </form>

                {#if success}
                    <SucessMessage />
                {/if}
            </div>
        </article>
    </div>
</section>