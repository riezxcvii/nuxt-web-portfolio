<template>
    <div class="bg-[#111b25]">
        <div class="sticky top-0 py-4 md:px-0 px-3">
            <nav class="hexagon m-auto px-2 py-2" :style="{ '--all': isMobile ? '5%' : '2%' }">
                <div class="flex mx-auto items-center justify-center justify-between px-4">
                    <div>
                        <span class="text-white md:text-2xl font-black uppercase tracking-wide cursor-default select-none">Portfolio</span>
                    </div>

                    <!-- navlinks (desktop view) -->
                    <div class="my-auto md:block hidden">
                        <ul v-for="page in pages" :key="page.id" class="text-white inline-block px-4 uppercase font-bold text-sm tracking-wide py-1">
                            <li class="flex cursor-pointer md:my-1">
                                <NuxtLink :to="page.link" class="flex">
                                    <img :src="page.logo" :alt="page.alt" class="w-5 mr-1 md:mt-[-0.1rem]">
                                    {{ page.name }}
                                </NuxtLink>
                            </li>
                        </ul>
                    </div>

                    <div class="flex md:gap-0 gap-4 items-center justify-center z-50">
                        <!-- download resume (mobile view) -->
                        <div>
                            <NuxtLink :to="cv" target="_blank">
                                <button class="py-1 px-4 bg-white rounded-lg font-bold uppercase text-sm tracking-wide">Resume</button>
                            </NuxtLink>
                        </div>

                        <!-- hamburger menu -->
                        <div class="flex items-end justify-items-end">
                            <button @click="toggleDrawer" type="button" class="inline-flex items-center p-0 w-6 h-9 justify-center text-sm rounded-lg md:hidden">
                                <span class="sr-only">Open main menu</span>
                                <svg class="w-5 h-5 z-40" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                                    <path stroke="white" strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M1 1h15M1 7h15M1 13h15" />
                                </svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- sidebar (mobile view) -->
                <SideBar v-if="drawer" :drawer="drawer" :toggleDrawer="toggleDrawer" :pages="pages" class="fixed" />
            </nav>

            <!-- sub menu in mobile view only -->
            <nav class="md:hidden block mx-2 bg-gray-50 dark:bg-gray-700">
                <div class="max-w-screen-xl px-4 py-3 mx-auto">
                    <div class="flex items-center">
                        <ul class="flex flex-row font-medium mt-0 space-x-8 rtl:space-x-reverse text-sm">
                            <li>
                                <a href="#" class="text-gray-900 dark:text-white hover:underline" aria-current="page">Home</a>
                            </li>
                            <li>
                                <a href="#" class="text-gray-900 dark:text-white hover:underline">Company</a>
                            </li>
                            <li>
                                <a href="#" class="text-gray-900 dark:text-white hover:underline">Team</a>
                            </li>
                            <li>
                                <a href="#" class="text-gray-900 dark:text-white hover:underline">Features</a>
                            </li>
                        </ul>
                    </div>
                </div>
            </nav>
        </div>

        <!-- slot for other components here -->
        <div>
            <slot />
        </div>
    </div>
</template>

<script setup>
import cv from '../assets/pdf/CV-Rieza-Marie-Banquillo.pdf'
import home from '../assets/logo/home.svg'
import skills from '../assets/logo/skills.svg'
import projects from '../assets/logo/projects.svg'

const drawer = ref(false)

const toggleDrawer = () => {
    drawer.value = !drawer.value
}

const pages = [
    { name: 'Home', link: '/', logo: home, alt: 'home.svg', id: 1 },
    { name: 'Tech Stack', link: '/techStack', logo: skills, alt: 'skills.svg', id: 2 },
    { name: 'Projects', link: '/projects', logo: projects, alt: 'projects.svg', id: 3 }
]
</script>
