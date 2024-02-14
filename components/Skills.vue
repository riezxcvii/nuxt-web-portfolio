<template>
    <div>
        <h1 class="font-black uppercase pb-6 tracking-wider my-auto text-[1.6rem] px-8 w-fit rounded-lg text-[#e6af2e]">
            SKILLS
        </h1>

        <!-- skill list -->
        <div class="flex px-8 h-full max-w-screen">
            <div ref="containerRef">
                <skillList v-slot:skillList :language="language" title="Languages" />
                <skillList v-slot:skillList :language="framework" title="Frameworks / Libraries" />
                <skillList v-slot:skillList :language="database" title="Database" />
                <skillList v-slot:skillList :language="web" title="Web Technologies" />
                <skillList v-slot:skillList :language="tools" title="Tools" />
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import skillList from '../layouts/skillList.vue'
import java from '../assets/logo/java.svg'
import javascript from '../assets/logo/javascript.svg'
import php from '../assets/logo/php.svg'
import react from '../assets/logo/react.svg'
import vue from '../assets/logo/vue.svg'
import tailwind from '../assets/logo/tailwind-css.svg'
import javaswing from '../assets/logo/javaswing.png'
import nextjs from '../assets/logo/next-js.svg'
import mysql from '../assets/logo/mysql.svg'
import html from '../assets/logo/html.svg'
import css from '../assets/logo/css.svg'
import canva from '../assets/logo/canva.svg'
import figma from '../assets/logo/figma.svg'
import vscode from '../assets/logo/vs-code.svg'
import git from '../assets/logo/git.svg'
import github from '../assets/logo/github.svg'
import netbeans from '../assets/logo/netbeans.png'
import nuxt from '../assets/logo/nuxt.svg'

const language = [
    { skill: "Java", logo: java, alt: "java.svg", id: 1 },
    { skill: "JavaScript", logo: javascript, alt: "javascript.svg", id: 2 },
    { skill: "PHP", logo: php, alt: "php.svg", id: 3 },
    { skill: "React", logo: react, alt: "react.svg", id: 4 },
    { skill: "Vue", logo: vue, alt: "vue.svg", id: 5 },
]

const framework = [
    { skill: "Tailwind CSS", logo: tailwind, alt: "tailwind-css.svg", id: 1 },
    { skill: "Java Swing", logo: javaswing, alt: "javaswing.png", id: 2 },
    { skill: "Next.js", logo: nextjs, alt: "next-js.svg", id: 3 },
    { skill: "Nuxt", logo: nuxt, alt: "nuxt.svg", id: 4 },
]

const database = [
    { skill: "MySQL", logo: mysql, alt: "mysql.svg", id: 1 }
]

const web = [
    { skill: "HTML", logo: html, alt: "html.svg", id: 1 },
    { skill: "CSS", logo: css, alt: "css.svg", id: 2 }
]

const tools = [
    { skill: "Canva", logo: canva, alt: "canva.svg", id: 1 },
    { skill: "Figma", logo: figma, alt: "figma.svg", id: 2 },
    { skill: "VS Code", logo: vscode, alt: "vs-code.svg", id: 3 },
    { skill: "Git", logo: git, alt: "git.svg", id: 4 },
    { skill: "GitHub", logo: github, alt: "github.svg", id: 5 },
    { skill: "NetBeans", logo: netbeans, alt: "netbeans.png", id: 6 }
]

const arraysToSort = [language, framework, database, web, tools]
arraysToSort.forEach(arr => arr.sort((a, b) => b.id - a.id))

const containerRef = ref(null);
</script>