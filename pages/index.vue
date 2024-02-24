<template>
    <div class="flex items-center justify-center my-auto h-screen">
        <div class="lg:mt-[-5rem] md:mt-[-6.5rem] mt-[-10rem]">
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
                            Front-end Web Developer
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
            <Contact />
        </div>
    </div>
</template>

<script setup>
import rieza from '../assets/image/rmjb.png'
</script>
