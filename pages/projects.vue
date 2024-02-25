<template>
    <div class="flex items-center justify-center min-h-screen min-w-screen">
        <!-- project lists -->
        <ul ref="projectList"
            class="items-center mx-auto h-full px-6 py-8 md:grid md:grid-cols-2 block justify-start gap-16 md:space-y-0 space-y-8">
            <li v-for="project in projects" key="project.id"
                class="text-black rounded-b-[1rem] rounded-t-[30rem] md:p-6 p-4 bg-[#D7CEC2]">
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
    </div>
</template>

<script setup>
import anslmsD from '../assets/image/desktop-ans-lms.png'
import anslmsM from '../assets/image/mobile-ans-lms.png'
import stackschedD from '../assets/image/desktop-stack-sched.png'
import stackschedM from '../assets/image/mobile-stack-sched.png'
import appointment from '../assets/image/desktop-appointment-system.png'
import inventory from '../assets/image/desktop-inventory-system.png'

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
            { name: 'Repository', url: 'https://github.com/rieza-ix/library-management-system.git' },
            { name: 'Website', url: 'http://anslibrary.infinityfreeapp.com/' },
        ],
        id: 1,
    },
    {
        title: "StackTrek Scheduling System",
        description: "Next.js • Tailwind CSS • Prisma • Supabase",
        desktop: stackschedD,
        mobile: stackschedM,
        mobileVisibility: "block",
        alt: "StackSched - Scheduling Page",
        links: [
            { name: 'Prototype', url: 'https://www.figma.com/proto/UF6Lf0hGmFoIIde3Q5pPR2/Scheduling-System?type=design&node-id=1-2&t=h0cyhoUJgxpLaXCY-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A2&mode=design' },
            { name: 'Repository', url: 'https://github.com/Stacktrek-Training/stack-sched.git' },
        ],
        id: 2,
    },
    {
        title: "Appointment System",
        description: "Java • Java Swing • JDBC • MySQL",
        desktop: appointment,
        mobileVisibility: "hidden my-auto mr-[-2rem]",
        alt: "Appointment System - Login Page",
        links: [
            { name: 'Repository', url: 'https://github.com/rieza-ix/java-appointment-system.git' },
        ],
        id: 3,
    },
    {
        title: "Inventory System",
        description: "Java • Java Swing • JDBC • MySQL",
        desktop: inventory,
        mobileVisibility: "hidden my-auto",
        alt: "Inventory System - Dashboard Page",
        links: [
            { name: 'Prototype', url: 'https://www.figma.com/proto/ijlwB8FBESsBKHYa2OK8e4/Java-Inventory-System?type=design&node-id=1-2&t=cO6DQPGvZQY4XasA-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A2&mode=design' },
            { name: 'Repository', url: 'https://github.com/rieza-ix/inventory-system.git' },
        ],
        id: 4,
    },
]
</script>
