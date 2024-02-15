<template>
    <div>
        <div class="relative mx-auto border-black md:border-[10px] border-[8px] rounded-t-xl w-full h-fit bg-black">
            <!-- screen image -->
            <div class="rounded-lg overflow-hidden md:w-[18rem] w-[100%]">
                <img :src="desktop" class="dark:hidden h-[13vh] md:h-full w-full rounded-lg my-0" :alt="alt" />
            </div>
        </div>
        <div class="relative mx-auto bg-white shadow-xl rounded-b-xl h-[1.6vh] max-w-[301px] md:h-[20px] md:max-w-[512px]">
        </div>
        <div class="relative mx-auto bg-white shadow-xl rounded-b-md h-[3vh] max-w-[26%] md:h-[30px] md:max-w-[85px]">
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    desktop: String,
    alt: String
})

const { desktop, alt } = props
</script>
