<template>
    <div>
        <div>
            <div class="flex md:px-8 px-6 w-full md:py-0 md:max-h-screen h-[79vh] my-auto mt-8">
                <!-- previous button -->
                <img :src="previous" id="previous" class="w-12 font-extrabold md:block hidden ml-4" alt="Go to previous"
                    @click="scrollProjects('left')" />

                <!-- project lists -->
                <ul ref="projectList"
                    class="items-center mx-auto overflow-x-auto overflow-y-auto px-4 py-2 md:flex block justify-start gap-8 md:space-y-0 space-y-8">
                    <li v-for="project in projects" key="project.id"
                        class="text-black rounded-b-[1rem] rounded-t-[30rem] md:p-6 p-4 transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-105 duration-300 bg-[#D7CEC2]">
                        <!-- mockups -->
                        <div class="flex justify-between md:space-x-6 space-x-1">
                            <!-- desktop computer mockup -->
                            <div class="m-auto">
                                <DesktopMockup :desktop="project.desktop" :alt="project.alt" />
                            </div>
                            <!-- phone mockup -->
                            <div :class="project.mobileVisibility">
                                <MobileMockup :mobile="project.mobile" :alt="project.alt" />
                            </div>
                        </div>
                        <!-- project details -->
                        <div>
                            <ProjectDetails :title="project.title" :description="project.description" :links="project.links" />
                        </div>
                    </li>
                </ul>

                <!-- next button -->
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

const projectList = ref(null)

const projects = [
    {
        title: "ANS Library Management System",
        description: "HTML • Tailwind CSS • PHP • MySQL",
        desktop: anslmsD,
        mobile: anslmsM,
        mobileVisibility: "block",
        alt: "ANS LMS - Login Page",
        links: [
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
        links: [
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
        links: [
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
        links: [
            { name: 'Prototype', url: 'https://www.figma.com/proto/ijlwB8FBESsBKHYa2OK8e4/Java-Inventory-System?type=design&node-id=1-2&t=cO6DQPGvZQY4XasA-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A2&mode=design' },
            { name: 'GitHub', url: 'https://github.com/rieza-ix/inventory-system.git' },
        ],
        id: 4,
    },
]

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
