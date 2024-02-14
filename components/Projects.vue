<template>
    <div>
        <div class="pt-[4rem] min-h-screen flex flex-col">
            <h1
                class="font-black uppercase pb-6 tracking-wider my-auto md:text-[1.5rem] text-xl pl-6 w-fit rounded-lg text-[#e6af2e]">
                APPLICATION SYSTEMS
            </h1>

            <div class="flex md:px-8 px-6 w-full md:py-0 py-2 md:h-full h-[79vh] my-auto">
                <img :src="previous" id="previous" class="w-12 font-extrabold md:block hidden ml-4" alt="Go to previous"
                    @click="scrollProjects('left')" />
                <!-- project lists -->
                <ul ref="projectList"
                    class="items-center mx-auto overflow-x-auto overflow-y-auto px-4 py-2 md:flex block justify-start gap-8 md:space-y-0 space-y-8">
                    <li v-for="p in projects" key="p.id"
                        class="text-black rounded-b-[1rem] rounded-t-[30rem] md:p-6 p-4 transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-105 duration-300 bg-[#D7CEC2]">
                        <div class="flex justify-between md:space-x-6 space-x-1">
                            <!-- desktop computer mockup -->
                            <div class="m-auto mockup">
                                <div
                                    class="relative mx-auto border-black md:border-[10px] border-[8px] rounded-t-xl w-full h-fit bg-black">
                                    <!-- screen image -->
                                    <div class="rounded-lg overflow-hidden md:w-[18rem] w-[100%]">
                                        <img :src="p.desktop" class="dark:hidden h-[13vh] md:h-full w-full rounded-lg my-0"
                                            :alt="p.alt" />
                                    </div>
                                </div>
                                <div
                                    class="relative mx-auto bg-white shadow-xl rounded-b-xl h-[1.6vh] max-w-[301px] md:h-[20px] md:max-w-[512px]">
                                </div>
                                <div
                                    class="relative mx-auto bg-white shadow-xl rounded-b-md h-[3vh] max-w-[26%] md:h-[30px] md:max-w-[85px]">
                                </div>
                            </div>

                            <!-- phone mockup -->
                            <div :class="p.mobileVisibility" class="mockup">
                                <div
                                    class="relative m-auto border-black md:border-[10px] border-[6px] md:rounded-[2rem] rounded-[1.1rem] md:h-[231px] h-[19.6vh] md:w-[130px] w-[4.8rem] shadow-xl">
                                    <!-- notch -->
                                    <div
                                        class="md:w-[60px] w-[38px] md:h-[12px] h-[9.5px] bg-black top-0 mt-[-0.35rem] rounded-b-[1rem] left-1/2 -translate-x-1/2 absolute">
                                    </div>
                                    <!-- volume up -->
                                    <div
                                        class="md:h-[30px] h-[20px] w-[3px] bg-black absolute md:-start-[12px] -start-[7px] md:top-[40px] top-[20px] rounded-s-lg">
                                    </div>
                                    <!-- volume down -->
                                    <div
                                        class="md:h-[30px] h-[20px] w-[3px] bg-black absolute md:-start-[12px] -start-[7px] md:top-[80px] top-[50px] rounded-s-lg">
                                    </div>
                                    <!-- power button -->
                                    <div
                                        class="md:h-[40px] h-[25px] w-[3px] bg-black absolute md:-end-[12px] -end-[7px] md:top-[58px] top-[33px] rounded-e-lg">
                                    </div>
                                    <div
                                        class="md:rounded-[1.3rem] rounded-[0.7rem] overflow-hidden w-full h-full bg-white">
                                        <!-- screen image -->
                                        <img :src="p.mobile" class="dark:hidden w-full h-full" :alt="p.alt" />
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div
                            class="flex flex-col items-center justify-end h-max space-y-2 w-full text-center tracking-wide md:pt-4 pt-2 p-2">
                            <!-- project title -->
                            <span class="md:text-lg text-base font-bold uppercase">{{ p.title }}</span>
                            <span class="md:text-sm text-xs uppercase">
                                {{ p.description }}
                            </span>

                            <div v-if="p.link && p.link.length > 0"
                                class="w-full flex justify-center items-center space-x-4">
                                <div v-for="link in p.link" :key="link.url">
                                    <NuxtLink :to="link.url" target="_blank">
                                        <button
                                            class="bg-[#e6af2e] md:px-6 px-4 py-1 rounded-lg md:text-sm text-xs font-bold uppercase tracking-wide">{{
                                                link.name }}</button>
                                    </NuxtLink>
                                </div>
                            </div>
                        </div>
                    </li>
                </ul>
                <img :src="next" id="next" class="w-12 font-extrabold md:block hidden ml-4" alt="Go to next"
                    @click="scrollProjects('right')" />
            </div>
        </div>
    </div>
</template>

<script setup>
import anslmsD from '../assets/image/desktop-ans-lms.png'
import anslmsM from '../assets/image/mobile-ans-lms.png'
import stackschedD from '../assets/image/desktop-stack-sched.png'
import stackschedM from '../assets/image/mobile-stack-sched.png'
import appointment from '../assets/image/desktop-appointment-system.png'
import inventory from '../assets/image/desktop-inventory-system.png'
import previous from '../assets/logo/previous.svg'
import next from '../assets/logo/next.svg'

const projects = [
    {
        title: "ANS Library Management System",
        description: "HTML • Tailwind CSS • PHP • MySQL",
        desktop: anslmsD,
        mobile: anslmsM,
        mobileVisibility: "block",
        alt: "ANS LMS - Login Page",
        link: [
            { name: 'GitHub', url: 'https://github.com/rieza-ix/library-management-system.git' },
            { name: 'Website', url: 'http://anslibrary.infinityfreeapp.com/' },
        ],
        id: 1,
    },
    {
        title: "StackTrek Scheduling System",
        description: "Next.js • Tailwind CSS • Prisma • Supabase",
        github: "",
        desktop: stackschedD,
        mobile: stackschedM,
        mobileVisibility: "block",
        alt: "StackSched - Scheduling Page",
        link: [
            { name: 'Prototype', url: 'https://www.figma.com/proto/UF6Lf0hGmFoIIde3Q5pPR2/Scheduling-System?type=design&node-id=1-2&t=h0cyhoUJgxpLaXCY-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A2&mode=design' },
            { name: 'GitHub', url: 'https://github.com/Stacktrek-Training/stack-sched.git' },
        ],
        id: 2,
    },
    {
        title: "Appointment System",
        description: "Java • Java Swing • JDBC • MySQL",
        github: "",
        desktop: appointment,
        mobileVisibility: "hidden my-auto mr-[-2rem]",
        alt: "Appointment System - Login Page",
        link: [
            { name: 'GitHub', url: 'https://github.com/rieza-ix/java-appointment-system.git' },
        ],
        id: 3,
    },
    {
        title: "Inventory System",
        description: "Java • Java Swing • JDBC • MySQL",
        github: "",
        desktop: inventory,
        mobileVisibility: "hidden my-auto",
        alt: "Inventory System - Dashboard Page",
        link: [
            { name: 'Prototype', url: 'https://www.figma.com/proto/ijlwB8FBESsBKHYa2OK8e4/Java-Inventory-System?type=design&node-id=1-2&t=cO6DQPGvZQY4XasA-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A2&mode=design' },
            { name: 'GitHub', url: 'https://github.com/rieza-ix/inventory-system.git' },
        ],
        id: 4,
    },
]

const projectList = ref(null)

const scrollProjects = (direction) => {
    const container = projectList.value

    if (container) {
        const scrollAmount = 500

        let scrollValue;
        if (direction === 'left') {
            scrollValue = container.scrollLeft - scrollAmount;
        } else if (direction === 'right') {
            scrollValue = container.scrollLeft + scrollAmount;
        }

        container.scrollTo({
            left: scrollValue,
            behavior: 'smooth'
        })
    }
}
</script>
