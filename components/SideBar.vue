<template>
    <div class="drawer">
        <div @click.stop="toggleDrawer" v-if="drawer"
            class="bg-gray-900 bg-opacity-50 w-full z-50 fixed top-0 right-0 h-screen p-4 overflow-y-auto transition-transform">
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
                    <li v-for="page in pages" :key="page.id" class="flex py-2 h-fit text-sm tracking-wide">
                        <NuxtLink :href="page.link"
                            class="flex text-white rounded md:p-0 pt-[0.3rem] uppercase tracking-wide">
                            <img :src="page.logo" :alt="page.alt" class="w-5 mr-1">
                            {{ page.name }}
                        </NuxtLink>
                    </li>
                </ul>

                <!-- profile links (mobile view) -->
                <ul class="space-y-2 font-medium mt-8">
                    <h3 class="text-white py-2 mt-8 uppercase tracking-wide">PROFILE LINKS</h3>
                    <hr class="border-white" />
                    <li v-for="profile in profiles" :key="profile.id" class="flex py-2 h-fit text-sm tracking-wide">
                        <img :src="profile.logo" :alt="profile.alt" class="w-5 mr-1 mt-1" />
                        <NuxtLink :href="profile.link" target="_blank"
                            class="flex text-white rounded md:p-0 pt-[0.3rem] tracking-wide uppercase">
                            {{ profile.name }}
                        </NuxtLink>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
import gmail from '../assets/logo/inbox.svg'
import linkedin from '../assets/logo/user-profile.svg'
import github from '../assets/logo/folder.svg'

const profiles = [
    { name: 'G-Mail', link: 'mailto:rizmarezlo@gmail.com', alt: 'gmail.svg', logo: gmail, id: 1 },
    { name: 'Linkedin', link: 'https://www.linkedin.com/in/riezamarie-banquillo/', alt: 'linkedin.svg', logo: linkedin, id: 2 },
    { name: 'GitHub', link: 'https://github.com/rieza-ix', alt: 'github.svg', logo: github, id: 3 },
]

const props = defineProps({
    drawer: Boolean,
    toggleDrawer: Function,
    pages: Array
})
</script>
