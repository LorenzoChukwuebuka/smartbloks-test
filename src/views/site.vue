<script lang='ts' setup>
import Sidebar from "../components/Sidebar.vue";
import Preview from "./preview.vue";
</script>

<template>
    <div class="flex h-screen">
        <div class="w-1/5 bg-gray-50 border-r shadow">
            <Sidebar />
        </div>
        <div class="w-4/5 p-3">
            <div class="border h-full flex flex-col rounded">
                <div class="h-16 px-3 flex items-center border-b">
                    <div
                        class="border px-2 py-1 bg-gray-100 flex item-center justify-center rounded"
                    >
                        <i class="ri-global-line text-gray-500"></i>
                        <small class="text-xs text-gray-600 leading-0 mt-1 ml-1"
                            >https://testsite.smartbloks.site</small
                        >
                    </div>
                </div>


                <!-- The IFRAME is the problem and issue with the codebase..
                
                took me awhile to figure out. I was wondering what was wrong (lol).

                The iframe is the reason why the  "hello" state was mutating in the store but not mutating 

                in the preview page/component...

                I added watchers to figure out what was going on.

                Isolated Context:

                An iframe operates in a separate browser context from the parent page. This means:
                The iframe does not have direct access to the parent page's JavaScript environment, including Pinia state.
                Communication between the parent page and iframe must be explicitly set up (e.g., using window.postMessage).

                (from google)

                another solution will be to use a <div class=""></div> instead of an iframe. this way everything works fine and from the same
                browser window.

                -->

                <!-- original code -->
                <!-- <iframe class="w-full flex-1" src="/preview"></iframe> -->

                <!-- so this is my solution  -->
                 <div class="w-full flex-1"> <Preview/>  </div>
            </div>
        </div>
    </div>
</template>



<style lang='postcss' scoped></style>