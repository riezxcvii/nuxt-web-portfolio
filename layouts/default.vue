<template>
    <div>
        <!-- animated background template -->
        <div>
            <ul class="background z-10 h-full">
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
            </ul>
        </div>

        <div class="sticky top-0">
            <nav class="bg-[#191716] p-4 justify-between flex my-auto shadow-xl">
                <div>
                    <span
                        class="text-white text-2xl font-black uppercase tracking-wide md:ml-2 cursor-default select-none md:pl-1 pl-3">Portfolio
                    </span>
                </div>

                <!-- navlinks (desktop view) -->
                <div class="my-auto md:block hidden">
                    <ul v-for="page in pages" :key="page.id"
                        class="text-white inline-block px-4 uppercase font-bold text-sm tracking-wide py-1">
                        <li class="flex cursor-pointer md:my-1">
                            <img :src="page.logo" :alt="page.alt" class="w-5 mr-1 md:mt-[-0.1rem]">
                            <NuxtLink :to="page.link">{{ page.name }}</NuxtLink>
                        </li>
                    </ul>
                </div>

                <div class="flex gap-4">
                    <!-- download resume (mobile view) -->
                    <div>
                        <NuxtLink :to="cv" target="_blank">
                            <button class="py-2 px-6 bg-white rounded-lg font-bold uppercase text-sm tracking-wide">
                                Resume
                            </button>
                        </NuxtLink>
                    </div>

                    <!-- humberger menu -->
                    <div class="flex items-end justify-items-end">
                        <button @click="toggleDrawer" type="button"
                            class="inline-flex items-center p-0 w-6 h-9 justify-center text-sm rounded-lg md:hidden">
                            <span class="sr-only">Open main menu</span>
                            <svg class="w-5 h-5 z-40" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                                <path stroke="white" strokeLinecap="round" strokeLinejoin="round" strokeWidth="2"
                                    d="M1 1h15M1 7h15M1 13h15" />
                            </svg>
                        </button>
                    </div>
                </div>

                <!-- sidebar (mobile view) -->
                <SideBar :drawer="drawer" :toggleDrawer="toggleDrawer" :pages="pages" class="fixed" />
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
    { name: 'Skills', link: '/skills', logo: skills, alt: 'skills.svg', id: 2 },
    { name: 'Projects', link: '/projects', logo: projects, alt: 'projects.svg', id: 3 }
]
</script>
