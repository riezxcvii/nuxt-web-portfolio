<template>
    <div>
        <div
            class="border-black md:border-[10px] border-[6px] md:rounded-[2rem] rounded-[1.1rem] md:h-[231px] h-[19.6vh] md:w-[130px] w-[4.8rem] shadow-xl">
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
