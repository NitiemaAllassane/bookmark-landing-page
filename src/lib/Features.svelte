<script>
  import TabOne from "./components/TabOne.svelte";
  import TabThree from "./components/TabThree.svelte";
  import TabTwo from "./components/TabTwo.svelte";

    let activeTab = $state("tab1");
</script>



<section class=" mb-32">
    <div class="container">
        <article class=" mb-12">
            <div class=" max-w-full md:max-w-[600px] mx-auto">
                <h2 class=" text-center text-3xl text-blue-950 font-[600] mb-4 md:mb-6 ">Features</h2>
                <p class="text-center text-gray-500">
                    Our aim is to make it quick and easy for you to access your favourite websites. 
                    Your bookmarks sync between your devices so you can access them on the go.
                </p>
            </div>
        </article>
        <article>
            <nav class="flex flex-col md:flex-row mb-16 md:mb-20">
                {#each ["tab1", "tab2", "tab3"] as tab, index}
                    <button
                        type="button"
                        role="tab"
                        aria-selected={activeTab === tab}
                        onclick={() => activeTab = tab}
                        class={`w-full py-3 md:p-6 text-[1.1em] font-[400] cursor-pointer transition duration-200
                            flex justify-center items-center border-gray-500 relative
                            ${index === 0 ? "border-t-1 md:border-t-0 md:border-b-1" : ""}
                            ${index === 1 ? "border-y-1 md:border-t-0" : ""}
                            ${index === 2 ? "border-b-1" : ""}
                            ${activeTab === tab ? "text-blue-950 after:content-[''] after:absolute after:bottom-0 after:left-1/2 after:translate-x-[-50%] after:w-[80%] after:h-[5px] after:bg-red-400" : "text-gray-500 hover:text-red-400"}
                        `}
                    >
                        {tab === "tab1" ? "Simple Bookmarking" : tab === "tab2" ? "Speedy Searching" : "Easy Sharing"}
                    </button>
                {/each}
            </nav>
            <div class="content">
                {#if activeTab === "tab1"}
                    <TabOne />
                {:else if activeTab === "tab2"}
                    <TabTwo />
                {:else}
                    <TabThree />
                {/if}
            </div>
        </article>
    </div>
</section>