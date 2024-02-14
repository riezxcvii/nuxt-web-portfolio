<template>
    <div>
        <nav class="bg-[#191716] p-4 justify-between flex my-auto shadow-xl">
            <div>
                <span
                    class="text-white text-2xl font-black uppercase tracking-wide md:ml-2 cursor-default select-none">Portfolio
                </span>
            </div>

            <!-- navlinks (dekstop view) -->
            <div class="my-auto md:block hidden">
                <ul v-for="s in section" :key="s.link"
                    class="text-white inline-block px-4 uppercase font-bold text-sm tracking-wide py-1">
                    <li class="flex cursor-pointer md:my-1">
                        <img :src="s.logo" :alt="s.alt" class="w-5 mr-1 md:mt-[-0.1rem]">
                        <NuxtLink :to="s.link">{{ s.name }}</NuxtLink>
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
                <div>
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
            <div @click.stop="toggleDrawer" v-if="drawer"
                class="drawer bg-gray-900 bg-opacity-50 w-full fixed top-0 right-0 z-40 h-screen p-4 overflow-y-auto transition-transform">

                <div class="bg-[#191716] w-60 fixed top-0 right-0 z-40 h-screen py-4 px-6 overflow-y-auto">
                    <!-- x button in drawer (mobile view) -->
                    <button type="button" @click.stop="toggleDrawer"
                        class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 absolute top-2.5 end-2.5 inline-flex items-center justify-center">
                        <svg class="w-3 h-3" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14">
                            <path stroke="white" strokeLinecap="round" strokeLinejoin="round" strokeWidth="2"
                                d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6" />
                        </svg>
                        <span class="sr-only">Close menu</span>
                    </button>

                    <!-- navlinks (mobile view) -->
                    <ul class="space-y-2 font-medium mt-8">
                        <h3 class="text-white py-2 uppercase tracking-wide">NAVIGATION LINKS</h3>
                        <hr class="border-white" />

                        <li v-for="s in section" :key="s.link" class="flex py-2 h-fit text-sm tracking-wide">
                            <img :src="s.logo" :alt="s.alt" class="w-5 mr-1 mt-1">
                            <NuxtLink :href="s.link"
                                class="flex text-white rounded md:p-0 pt-[0.3rem] uppercase tracking-wide">
                                {{ s.name }}
                            </NuxtLink>
                        </li>
                    </ul>

                    <!-- profile links (mobile view) -->
                    <ul class="space-y-2 font-medium mt-8">
                        <h3 class="text-white py-2 mt-8 uppercase tracking-wide">PROFILE LINKS</h3>
                        <hr class="border-white" />

                        <li v-for="p in profile" :key="p.link" class="flex py-2 h-fit text-sm tracking-wide">
                            <img :src="p.logo" :alt="p.alt" class="w-5 mr-1 mt-1" />
                            <NuxtLink :href="p.link" target="_blank"
                                class="flex text-white rounded md:p-0 pt-[0.3rem] tracking-wide uppercase">
                                {{ p.name }}
                            </NuxtLink>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script setup>
import cv from '../assets/pdf/CV-Rieza-Marie-Banquillo.pdf'
import home from '../assets/logo/home.svg'
import skills from '../assets/logo/skills.svg'
import projects from '../assets/logo/projects.svg'
import gmail from '../assets/logo/inbox.svg'
import linkedin from '../assets/logo/user-profile.svg'
import github from '../assets/logo/folder.svg'

const drawer = ref(false)

const toggleDrawer = () => {
    drawer.value = !drawer.value
}

const section = [
    { name: 'Home', link: '#home', logo: home, alt: 'home.svg' },
    { name: 'Skills', link: '#skills', logo: skills, alt: 'skills.svg' },
    { name: 'Projects', link: '#projects', logo: projects, alt: 'projects.svg' }
]

const profile = [
    { name: 'G-Mail', link: 'mailto:rizmarezlo@gmail.com', alt: 'gmail.svg', logo: gmail },
    { name: 'Linkedin', link: 'https://www.linkedin.com/in/riezamarie-banquillo/', alt: 'linkedin.svg', logo: linkedin },
    { name: 'GitHub', link: 'https://github.com/rieza-ix', alt: 'github.svg', logo: github },
]
</script>
