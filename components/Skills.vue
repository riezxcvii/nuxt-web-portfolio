<template>
    <div>
        <!-- skill category title -->
        <h1 class="text-white font-black uppercase tracking-wider my-0 text-xl w-fit rounded-lg">
            {{ categoryName }}
        </h1>

        <!-- skill list -->
        <div>
            <ul
                class="h-max py-4 mb-4 lg:w-[75rem] md:w-[50rem] w-[19rem] items-center mx-auto overflow-x-auto flex justify-start md:gap-6 gap-4">
                <li v-for="skill in skillCategory" :key="skill.id" class="bg-white w-max text-black rounded-md px-4 py-2">
                    <div class="flex w-full items-center justify-end h-full w-max">
                        <img :src="skill.logo" class="w-auto h-7 justify-between m-auto mr-2" :alt="skill.alt" />
                        <span class="font-bold uppercase tracking-wide md:text-sm text-sm align-middle my-auto flex">
                            {{ skill.name }}
                        </span>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    skillCategory: Array,
    categoryName: String
});

const skillCategory = ref(props.skillCategory);
const categoryName = props.categoryName;
</script>
