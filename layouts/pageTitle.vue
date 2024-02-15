<template>
    <slot>
        <!-- page title here -->
        <h1
            class="font-black uppercase pb-6 tracking-wider my-auto md:text-[1.5rem] text-2xl pl-6 w-fit rounded-lg text-[#e6af2e]">
            {{ pageTitle }}
        </h1>

        <!-- slot for page content here -->
        <div>
            <slot />
        </div>
    </slot>
</template>

<script setup>
const props = defineProps({
    pageTitle: String
})

const pageTitle = props.pageTitle
</script>
