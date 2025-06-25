<script>
    import { ChevronDown } from 'lucide-svelte';
    import { backOut } from 'svelte/easing';
    import { slide } from 'svelte/transition';
  import MoreButton from './components/MoreButton.svelte';

    let faqs = [
        {
            question: "What is Bookmark?",
            answer: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.",
            isOpened: false
        },
        {
            question: "How can I request a new browser?",
            answer: "Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet.",
            isOpened: false
        },
        {
            question: "Is there a mobile app?",
            answer: "Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed sollicitudin ex et ultricies bibendum.",
            isOpened: false
        },
        {
            question: "What about other Chromium browsers?",
            answer: "Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit.",
            isOpened: false
        }
    ];

    function toggleFaq(index) {
		faqs = faqs.map((faq, i) => ({
			...faq,
			isOpened: i === index ? !faq.isOpened : false
		}));
	}


</script>

<section class=" mb-32">
    <div class="container">
        <article class=" mb-16">
            <div class=" max-w-full md:max-w-[600px] mx-auto">
                <h2 class=" text-center text-3xl text-blue-950 font-[600] mb-4 md:mb-6 ">
                    Frequently Asked Questions
                </h2>
                <p class="text-center text-gray-500">
                    Here are some of our FAQs. If you have any other questions you’d like 
                    answered please feel free to email us.
                </p>
            </div>
        </article>
        <article class=" max-w-full md:max-w-[600px] mx-auto mb-11">
            {#each faqs as faq, i}
                <div class=" {i === 0 ? `md:border-t`: ""} border-b border-gray-500">
                    <button 
                        class=" group py-4 w-full flex justify-between items-center cursor-pointer"
                        onclick={() => toggleFaq(i)}
                    >
                        <span class=" text-blue-950 text-[1em] text-start font-[400] group-hover:text-red-400 transition-colors duration-200 ">
                            { faq.question }
                        </span>
                        <ChevronDown 
                            class=" cursor-pointer transition-transform duration-350 {faq.isOpened ? `transform rotate-180 text-red-400` : "text-blue-600"} " 
                            size={28} 
                            strokeWidth={2.5} />
                    </button>
                    {#if faq.isOpened}
                        <p 
                            class="faq-p text-gray-500 pt-9 pb-6"
                            in:slide={{duration: 300, easing: backOut}}
                            out:slide={{ duration: 300}}
                        >
                            { faq.answer }
                        </p>
                    {/if}
                </div>
            {/each}
        </article>
        <div class=" flex justify-center items-center">
            <MoreButton hidden={false} />
        </div>
    </div>
</section>