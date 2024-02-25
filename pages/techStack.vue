<template>
    <div ref="stackRef"
        class="grid md:grid-cols-3 grid-cols-1 p-8 gap-8 items-center justify-center max-w-screen my-auto min-h-screen">
        <Stack title="Application Development" :techStack="applicationDev" />
        <Stack title="Web Development" :techStack="webDev" />
        <Stack title="Full-Stack Development" :techStack="fullStackDev" />
        <Stack title="Design Tools" :techStack="design" />
        <Stack title="Version Control" :techStack="versionControl" />
        <Stack title="Integrated Development Environment (IDE)" :techStack="ide" />
    </div>
</template>

<script setup>
import html from '../assets/logo/html.svg'
import css from '../assets/logo/css.svg'
import tailwindcss from '../assets/logo/tailwind-css.svg'
import javascript from '../assets/logo/javascript.svg'
import react from '../assets/logo/react.svg'
import nextjs from '../assets/logo/next-js.svg'
import vue from '../assets/logo/vue.svg'
import nuxt from '../assets/logo/nuxt.svg'
import java from '../assets/logo/java.svg'
import javaswing from '../assets/logo/javaswing.png'
import jdbc from '../assets/logo/jdbc.png'
import mysql from '../assets/logo/mysql.svg'
import phpmyadmin from '../assets/logo/phpmyadmin.png'
import xampp from '../assets/logo/xampp.svg'
import php from '../assets/logo/php.svg'
import figma from '../assets/logo/figma.svg'
import canva from '../assets/logo/canva.svg'
import git from '../assets/logo/git.svg'
import github from '../assets/logo/github.svg'
import vscode from '../assets/logo/vs-code.svg'
import netbeans from '../assets/logo/netbeans.png'

const stackRef = ref(null)

const applicationDev = [
    { name: "Java", logo: java, alt: "java.svg", id: 1 },
    { name: "Java Swing", logo: javaswing, alt: "javaswing.png", id: 2 },
    { name: "JDBC", logo: jdbc, alt: "jdbc.png", id: 3 },
    { name: "MySQL", logo: mysql, alt: "mysql.svg", id: 4 },
    { name: "PhpMyAdmin", logo: phpmyadmin, alt: "phpmyadmin.png", id: 5 },
    { name: "XAMPP", logo: xampp, alt: "xampp.svg", id: 6 },
]

const webDev = [
    { name: "Vue", logo: vue, alt: "vue.svg", id: 1 },
    { name: "Nuxt", logo: nuxt, alt: "nuxt.svg", id: 2 },
    { name: "React", logo: react, alt: "react.svg", id: 3 },
    { name: "Next.js", logo: nextjs, alt: "nextjs.svg", id: 4 },
    { name: "HTML", logo: html, alt: "html.svg", id: 5 },
    { name: "CSS", logo: css, alt: "css.svg", id: 6 },
    { name: "Tailwind CSS", logo: tailwindcss, alt: "tailwind-css.svg", id: 7 },
    { name: "JavaScript", logo: javascript, alt: "javascript.svg", id: 8 },
]

const fullStackDev = [
    { name: "HTML", logo: html, alt: "html.svg", id: 1 },
    { name: "CSS", logo: css, alt: "css.svg", id: 2 },
    { name: "Tailwind CSS", logo: tailwindcss, alt: "tailwind-css.svg", id: 3 },
    { name: "JavaScript", logo: javascript, alt: "javascript.svg", id: 4 },
    { name: "PHP", logo: php, alt: "php.svg", id: 5 },
    { name: "MySQL", logo: mysql, alt: "mysql.svg", id: 6 },
    { name: "PhpMyAdmin", logo: phpmyadmin, alt: "phpmyadmin.svg", id: 7 },
    { name: "XAMPP", logo: xampp, alt: "xampp.svg", id: 8 },
]

const design = [
    { name: "Figma", logo: figma, alt: "figma.svg", id: 1 },
    { name: "Canva", logo: canva, alt: "canva.svg", id: 2 },
]

const versionControl = [
    { name: "Git", logo: git, alt: "git.svg", id: 1 },
    { name: "GitHub", logo: github, alt: "github.svg", id: 2 },
]

const ide = [
    { name: "VS Code", logo: vscode, alt: "vs-code.svg", id: 9 },
    { name: "NetBeans", logo: netbeans, alt: "netbeans.png", id: 6 },
]
</script>
