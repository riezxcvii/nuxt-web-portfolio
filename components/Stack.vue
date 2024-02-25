<template>
    <div
        class="bg-transparent pt-4 pb-8 px-8 rounded-lg shadow-lg lg:h-[55vh] md:h-[90vh] h-max shadow-[#e6af2e] border-t-4 border-[#D7CEC2]">
        <!-- tech stack category -->
        <h1 class="md:text-lg font-black uppercase tracking-wide my-4 mb-8 text-white">{{ title }}</h1>

        <!-- tech stack list -->
        <ul class="flex flex-wrap gap-2">
            <li v-for="stack in techStack" :key="stack.id"
                class=" flex justify-center items-center bg-white md:px-3 px-2 py-2 rounded-lg">
                <img :src="stack.logo" :alt="stack.alt" class="md:h-6 h-5 mr-1">
                <h2 class="text-xs uppercase">{{ stack.name }}</h2>
            </li>
        </ul>
    </div>
</template>

<script setup>
const props = defineProps({
    title: String,
    techStack: Object,
})

const title = props.title
const techStack = ref(props.techStack)
</script>
