<script setup>
import { Calendar, CheckCircle2, GraduationCap } from 'lucide-vue-next';
import educ from '../assets/educ.png';

const educationData = [
    {
        id: "1",
        degree: "Développeur Fullstack",
        institution: "WECODE by Epitech Côte d'Ivoire",
        duration: 'Janvier 2026 - Juillet 2026',
        details: "WE.CODE est une initiative portée par le programme Invest for Jobs / FORPRODE financée conjointement par la Coopération allemande et l’Union européenne et mise en œuvre avec les partenaires EPITECH et M-Studio.",
        image: ""

    },
    {
        id: "2",
        degree: "Formation en élèctricité et automatisme Industrielle",
        institution: "IKATEC",
        duration: '11 Avril 2025 - 15 Mai 2025',
        details: " Formation financée par l'Agence Emploi Jeunes et pilotée par IKATEC, au cours de laquelle nous avons été initiés à l'électricité industrielle et à l'automatisme.",
        image: ""

    },
    {
        id: "4",
        degree: "Formation en Impression et Design 3D, Intelligence Artificielle, Robotique (Etude des cartes Arduino)",
        institution: "Centre Ivoirien de Robotique & Centre Andrew Young",
        duration: '5 Mars 2024 - 31 Mai 2024',
        details: "Cette formation d'initiation m'a permis d'acquérir les fondamentaux de la modélisation et de l'impression 3D, de découvrir les bases de l'intelligence artificielle à travers une introduction au Machine Learning avec Python, et de maîtriser les premiers concepts de l'électronique grâce à une initiation à la programmation Arduino.",
        image: ""

    },
    {
        id: "5",
        degree: "Licence Informatique et Science du Numérique specialité Développement d'Application et E-services (DAS)",
        institution: "Université Virtuelle de Côte d'Ivoire (UVCI)",
        duration: 'Janvier 2020 - Août 2024',
        details: "Conception et développement d'applications (Web, Mobile) à travers les nouvelles technologies des outils de codification.",
        image: ""
    }

]
</script>


<template>
    <section class="text-white py-20 overflow-hidden" id="education">
        <div class="max-w-7-xl mx-auto px-6 lg:px-16">
            <div class="mb-16 flex flex-col items-center">
                <p class="text-primary text-sm upppercase mb-2 tracking-widest font-semibold">Learning Path</p>
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">Education</h2>
            </div>
            <div class="flex flex-col justify-center lg:flex-row items-center gap-16">
                <!-- <div class="w-full lg:w-5/12 flex justify-center lg:justify-start data-aos=fade-right">
                    <div class="relative">
                        <div class="absolute h-full w-full z-0 p-2 translate-x-4 translate-y-4 rounded-2xl shadow-lg border border-primary"></div>
                        <div class="relative z-1 bg-[#111a2e] rounded-2xl overflow-hidden border-[#1f1641]">
                            <img :src="educ" alt="Education" class="w-64 h-64 md:w-96 md:h-120 object-cover transform transition-transform duration-500 hover:scale-110">
                        </div>
                    </div>
                </div> -->
                <!-- Education Content -->
                <div class="w-full lg:w-7/12 space-y-6 " data-aos="fade-left">
                   <div v-for="edu in educationData" :key="edu.id" class="group relative p-4 sm:p-6 rounded-2xl bg-[#1f1641] transition-all duration-300 hover:border-primary/50">
                        <div class="flex flex-col lg:flex-row lg:items-start justify-between gap-4 mb-4">

                            <!-- Section Titre et Icône -->
                            <div class="flex items-start gap-3 w-full lg:max-w-[75%]">
                                <!-- Icône (taille fixe pour éviter l'écrasement) -->
                                <div class="flex-shrink-0 p-2 bg-[#050216] rounded-lg border border-primary/20 group-hover:border-primary transition-colors">
                                    <GraduationCap class="text-primary" :size="24" />
                                </div>
                                
                                <!-- Textes -->
                                <div class="min-w-0 flex-1">
                                    <h3 class="text-base sm:text-lg font-bold text-white group-hover:text-primary transition-colors break-words">
                                        {{ edu.degree }}
                                    </h3>
                                    <p class="text-gray-400 text-sm break-words">
                                        {{ edu.institution }}
                                    </p>
                                </div>
                            </div>

                            <!-- Badge Date (S'aligne à droite sur grand écran, passe en dessous sur mobile) -->
                            <div class="flex items-center gap-2 text-xs font-medium bg-[#050816] px-3 py-1 rounded-full border border-gray-700 self-start lg:self-center flex-shrink-0 w-fit">
                                <Calendar :size="14" class="text-primary" />
                                {{ edu.duration }}
                            </div>
                        </div>

                        <!-- Description -->
                        <p class="text-gray-400 text-sm leading-relaxed mb-4 break-words">
                            {{ edu.details }}
                        </p>

                        <!-- Badge Spécial -->
                        <div v-if="edu.image === 'Academie d\'Excellence'" class="flex items-center gap-2 text-[10px] uppercase tracking-wider text-primary font-bold">
                            <CheckCircle2 :size="12" />
                            {{ edu.image }}
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>