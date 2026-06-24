<script setup>
import proj1 from '../assets/postit.png'
import proj2 from '../assets/rotten.png'
import proj3 from '../assets/proj1.png'
import proj4 from '../assets/proj1.png'
import proj5 from '../assets/proj1.png'
import proj6 from '../assets/proj1.png'
// import { Link } from 'lucide-vue-next'

const projects = [
    {
        id:1,
        image: proj1,
        title: 'Post-it',
        desc: 'Site permettant de créer des notes afin de sauvegarder instantanément les tâches afin de fluidifier la gestion du temps réaliser en vue.js',
        techg: ['Vue.js', 'API REST', 'Tailwind'],
        Link: "https://stiky-post-it.vercel.app/"
    },
    {
        id:2,
        image: proj2,
        title: 'My rotten Tomatoes',
        desc: "Un site web consacré à la présentation et aux critiques de films. L'objectif est de proposer aux utilisateurs un espace leur permettant de découvrir de nouveaux films, accompagnés de descriptions, de notes et des avis du public réaliser",
        techg: ['next.js', 'MySql', 'Tailwind'],
        Link: "https://rottom-production.up.railway.app/"

    },
    {
        id:3,
        image: proj3,
        title: 'Intégration',
        desc: "réalisation d'interface web",
        techg: ['HTML5', 'CSS3', 'Tailwind'],
        Link: "#"

    },

]

</script>
<template>
    <section class="py-16 bg-gray-900" id="projects">
        <div class="container mx-auto px-4 max-w-7xl">
            <div class="text-center mb-10">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">
                    Projects.
                </h2>
                <div class="w-28 h-1 bg-primary mx-auto mt-2 rounded-2xl"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
                <div v-for="project in projects" :key="project.id" class="bg-gray-800 rounded-lg overflow-hidden shadow-sm hover:shadow-lg hover:scale-105 transition-all duration-300">
                    <img :src="project.image" :alt="project.title" class="w-full h-44 object-cover hover:opacity-90 transition-opacity duration-300">
                    
                    <a :href="project.Link" rel="noopener noreferrer" class="group block">
 <!-- target="_blank" -->
                    <div class="p-4">
                        <h3 class="text-lg font-semibold text-white group-hover:primary transition-colors">
                            {{ project.title }}
                        </h3>
                        <p class="text-gray-400 text-sm mt-1">
                            {{ project.desc }}
                        </p>
                        <div class="flex flex-wrap gap-1.5 mt-3">
                            <span v-for="(tech, idx) in project.techg" :key="idx" class="text-xs px-2 py-0.5 bg-gray-700 text-gray-300 rounded hover:bg-primary hover:text-white transition-colors duration-300">
                                {{ tech }}
                            </span>
                        </div>
                    </div>
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>