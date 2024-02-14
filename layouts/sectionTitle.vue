<template>
    <slot name="sectionName">
        <h1
            class="mt-8 font-black uppercase pb-6 tracking-wider my-auto md:text-[1.5rem] text-2xl pl-6 w-fit rounded-lg text-[#e6af2e]">
            {{ title }}
        </h1>

        <div>
            <slot />
        </div>
    </slot>
</template>

<script setup>
const props = defineProps({
    sectionName: String
})

const title = props.sectionName
</script>
