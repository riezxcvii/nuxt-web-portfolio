<template>
    <div class="contact flex items-center justify-center my-auto min-h-screen">
        <div class="lg:mt-[-5rem] md:mt-[-6.5rem] mt-[-10rem]">
            <!-- header -->
            <div class="md:flex lg:space-x-12 md:space-x-8 space-x-0 justify-between md:space-y-0 space-y-12">
                <!-- image -->
                <div
                    class="lg:w-[28rem] md:w-[18rem] w-10/12 bg-[#D7CEC2] px-8 rounded-br-[12rem] rounded-tl-[12rem] m-auto">
                    <img :src="rieza" alt="rmjb.png" />
                </div>

                <!-- other details -->
                <div
                    class="block lg:w-[36.2rem] md:w-[25.6rem] w-fit mx-auto md:py-20 mx-auto md:px-0 px-8 lg:space-y-5 md:space-y-3 space-y-3">
                    <div class="flex justify-between mb-0">
                        <h3
                            class="font-bold lg:text-3xl md:text-2xl text-xl text-white cursor-default select-none tracking-wide uppercase">
                            Hi, I'm
                        </h3>
                        <h3
                            class="font-bold text-black bg-[#e6af2e] rounded-md w-fit h-fit py-1 px-3 shadow-md lg:text-sm md:text-xs text-xs cursor-default select-none developer appear my-auto tracking-wide uppercase">
                            Software Developer
                        </h3>
                    </div>

                    <h1
                        class="myName font-black lg:text-[3.41rem] md:text-[2.4rem] text-3xl text-white uppercase cursor-default select-none whitespace-nowrap tracking-wide md:mb-2 mb-1">
                        Rieza Banquillo
                    </h1>

                    <hr class="border-2 md:mb-5 mb-4" />

                    <p
                        class="text-white lg:text-base md:text-sm text-sm whitespace-normal cursor-default select-none tracking-wider md:w-full font-bold ">
                        I'm dedicated to leveraging cutting-edge technologies to bring
                        your visions to life. Let's collaborate and elevate your digital
                        presence with expertise and creativity.
                    </p>
                </div>
            </div>

            <!-- profile links -->
            <div
                class="floatingLinks py-6 px-8 grid md:grid-cols-1 md:grid-rows-3 md:gap-0 grid-cols-3 grid-rows-1 gap-4 absolute right-0 bottom-0 m-0 mt-0 items-center justify-center z-10">
                <ul v-for="p in profile" :key="p.link">
                    <li>
                        <div class="flex items-center justify-center mx-auto">
                            <NuxtLink :href="p.link" target="_blank">
                                <img :src="p.logo" :alt="p.alt" class="w-[2rem] mx-auto my-3 shadow-lg" />
                            </NuxtLink>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
import rieza from '../assets/image/rmjb.png'
import gmail from '../assets/logo/gmail.svg'
import linkedin from '../assets/logo/linkedin.svg'
import github from '../assets/logo/github.svg'

const profile = [
    { name: 'G-Mail', link: 'mailto:rizmarezlo@gmail.com', alt: 'gmail.svg', logo: gmail },
    { name: 'Linkedin', link: 'https://www.linkedin.com/in/riezamarie-banquillo/', alt: 'linkedin.svg', logo: linkedin },
    { name: 'GitHub', link: 'https://github.com/rieza-ix', alt: 'github.svg', logo: github },
]
</script>
