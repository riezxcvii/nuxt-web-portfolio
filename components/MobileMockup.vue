<template>
    <div>
        <div
            class="relative m-auto border-black md:border-[10px] border-[6px] md:rounded-[2rem] rounded-[1.1rem] md:h-[231px] h-[19.6vh] md:w-[130px] w-[4.8rem] shadow-xl">
            <!-- notch -->
            <div
                class="md:w-[60px] w-[38px] md:h-[12px] h-[9.5px] bg-black top-0 mt-[-0.35rem] rounded-b-[1rem] left-1/2 -translate-x-1/2 absolute">
            </div>
            <!-- volume up -->
            <div
                class="md:h-[30px] h-[20px] w-[3px] bg-black absolute md:-start-[12px] -start-[7px] md:top-[40px] top-[20px] rounded-s-lg">
            </div>
            <!-- volume down -->
            <div
                class="md:h-[30px] h-[20px] w-[3px] bg-black absolute md:-start-[12px] -start-[7px] md:top-[80px] top-[50px] rounded-s-lg">
            </div>
            <!-- power button -->
            <div
                class="md:h-[40px] h-[25px] w-[3px] bg-black absolute md:-end-[12px] -end-[7px] md:top-[58px] top-[33px] rounded-e-lg">
            </div>
            <div class="md:rounded-[1.3rem] rounded-[0.7rem] overflow-hidden w-full h-full bg-white">
                <!-- screen image -->
                <img :src="mobile" class="dark:hidden w-full h-full" :alt="alt" />
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    mobile: String,
    alt: String
})

const { mobile, alt } = props
</script>
