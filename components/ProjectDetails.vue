<template>
    <div class="flex flex-col items-center justify-end h-max space-y-2 w-full text-center tracking-wide md:pt-4 mt-2 p-2">
        <!-- project title -->
        <span class="md:text-lg text-base font-bold uppercase">{{ title }}</span>
        <!-- project description -->
        <span class="md:text-sm text-xs uppercase">
            {{ description }}
        </span>
        <!-- button -->
        <div v-if="links && links.length > 0" class="w-full flex justify-center items-center space-x-4">
            <div v-for="link in links" :key="link.url">
                <NuxtLink :to="link.url" target="_blank">
                    <button
                        class="bg-[#e6af2e] px-4 py-1 rounded-lg md:text-sm text-xs font-bold uppercase tracking-wide">{{
                            link.name }}</button>
                </NuxtLink>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    title: String,
    description: String,
    links: Object
})

const { title, description, links } = props
</script>
