<template>
    <div>
        <!-- skill list -->
        <div class="flex mt-4 h-full">
            <div ref="listRef">
                <Skills :skillCategory="languages" categoryName="Languages" />
                <Skills :skillCategory="frameworks" categoryName="Frameworks / Libraries" />
                <Skills :skillCategory="databases" categoryName="Database" />
                <Skills :skillCategory="webs" categoryName="Web Technologies" />
                <Skills :skillCategory="tools" categoryName="Tools" />
            </div>
        </div>
    </div>
</template>

<script setup>
import Skills from '../components/Skills.vue'

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

const languages = [
    { name: "Java", logo: java, alt: "java.svg", id: 1 },
    { name: "JavaScript", logo: javascript, alt: "javascript.svg", id: 2 },
    { name: "PHP", logo: php, alt: "php.svg", id: 3 },
    { name: "React", logo: react, alt: "react.svg", id: 4 },
    { name: "Vue", logo: vue, alt: "vue.svg", id: 5 },
]

const frameworks = [
    { name: "Tailwind CSS", logo: tailwind, alt: "tailwind-css.svg", id: 1 },
    { name: "Java Swing", logo: javaswing, alt: "javaswing.png", id: 2 },
    { name: "Next.js", logo: nextjs, alt: "next-js.svg", id: 3 },
    { name: "Nuxt", logo: nuxt, alt: "nuxt.svg", id: 4 },
]

const databases = [
    { name: "MySQL", logo: mysql, alt: "mysql.svg", id: 1 }
]

const webs = [
    { name: "HTML", logo: html, alt: "html.svg", id: 1 },
    { name: "CSS", logo: css, alt: "css.svg", id: 2 }
]

const tools = [
    { name: "Canva", logo: canva, alt: "canva.svg", id: 1 },
    { name: "Figma", logo: figma, alt: "figma.svg", id: 2 },
    { name: "VS Code", logo: vscode, alt: "vs-code.svg", id: 3 },
    { name: "Git", logo: git, alt: "git.svg", id: 4 },
    { name: "GitHub", logo: github, alt: "github.svg", id: 5 },
    { name: "NetBeans", logo: netbeans, alt: "netbeans.png", id: 6 }
]

const arraysToSort = [languages, frameworks, databases, webs, tools]
arraysToSort.forEach(arr => arr.sort((a, b) => b.id - a.id))

const listRef = ref(null)
</script>
