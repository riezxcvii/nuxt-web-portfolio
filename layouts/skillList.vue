<template>
    <slot name="skillList">
        <h1 class="text-white font-black uppercase tracking-wider my-0 text-xl w-fit rounded-lg text-white">
            {{ title }}
        </h1>
        <div>
            <ul
                class="h-max py-4 mb-4 lg:w-[75rem] md:w-[50rem] w-[19rem] items-center mx-auto overflow-x-auto flex justify-start md:gap-8 gap-4">
                <li v-for="l in language" :key="l.id" class="bg-white w-max text-black rounded-md px-4 py-2">
                    <div class="flex w-full items-center justify-end h-full w-max">
                        <img :src="l.logo" class="w-auto h-7 justify-between m-auto mr-2" :alt="l.alt" />
                        <span class="font-bold uppercase tracking-wide md:text-sm text-sm align-middle my-auto flex">
                            {{ l.skill }}
                        </span>
                    </div>
                </li>
            </ul>
        </div>

    </slot>
</template>

<script setup>
import { ref } from 'vue';

const props = defineProps({
    language: Array,
    title: String
});

const language = ref(props.language);
const title = props.title;
</script>
