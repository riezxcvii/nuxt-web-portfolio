<template>
    <div>
        <div
            class="py-6 px-8 grid md:grid-cols-1 md:grid-rows-3 md:gap-0 grid-cols-3 grid-rows-1 gap-4 absolute right-0 bottom-0 m-0 mt-0 items-center justify-center z-10 md:block hidden">
            <ul v-for="profile in profiles" :key="profile.link">
                <li>
                    <div class="flex items-center justify-center mx-auto">
                        <NuxtLink :to="profile.link" target="_blank">
                            <img :src="profile.logo" :alt="profile.alt" class="w-[2rem] mx-auto my-3 shadow-lg" />
                        </NuxtLink>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script setup>
import gmail from '../assets/logo/gmail.svg'
import linkedin from '../assets/logo/linkedin.svg'
import github from '../assets/logo/github.svg'

const profiles = [
    { name: 'G-Mail', link: 'mailto:rizmarezlo@gmail.com', alt: 'gmail.svg', logo: gmail },
    { name: 'Linkedin', link: 'https://www.linkedin.com/in/riezamarie-banquillo/', alt: 'linkedin.svg', logo: linkedin },
    { name: 'GitHub', link: 'https://github.com/rieza-ix', alt: 'github.svg', logo: github },
]
</script>
