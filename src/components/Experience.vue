<script setup>
import { Briefcase, Building2, Calendar1 } from 'lucide-vue-next';
import { Icon } from '@iconify/vue'

const skills = [
    ['Langages', 
        { id: 1, name: 'HTML5', width: '80%', iconName: 'logos:html-5'},
        { id: 2, name: 'CSS3', width: '70%', iconName: 'logos:css-3'},
        { id: 3, name: 'php', width: '65%', iconName: 'logos:php' },
        { id: 4, name: 'Javascript', width: '70%', iconName: 'logos:javascript' },
        { id: 5, name: 'Python', width: '60%', iconName: 'logos:python' }
    ],
    ['Frontend', 
        { id: 1, name: 'Vue Js', width: '75%', iconName: 'logos:vue' },
        { id: 2, name: 'Next Js', width: '65%', iconName: 'logos:nextjs-icon' },
        { id: 3, name: 'React Js', width: '62%', iconName: 'logos:react' },
        { id: 4, name: 'Tailwind', width: '70%', iconName: 'logos:tailwindcss-icon'}

    ],
    ['Backend', 
        { id: 1, name: 'Laravel', width: '70%', iconName: 'logos:laravel' },
        { id: 2, name: 'Nest Js', width: '60%', iconName: 'logos:nestjs' },
        { id: 3, name: 'next Js', width: '60%', iconName: 'logos:nextjs-icon' }
    ],
    ['Autres outils', 
        { id: 1, name: 'Figma', width: '70%', iconName: 'logos:figma' },
        { id: 2, name: 'git', width: '80%', iconName: 'logos:git-icon' },
        { id: 3, name: 'github', width: '80%', iconName: 'logos:github-icon' },
        { id: 4, name: 'Postman', width: '75%', iconName: 'logos:postman-icon' }
    ]
]

const experiences = [
    {
        id: 1,
        role: 'Automaticien',
        company: 'IKATEC',
        date: '02 Juin 2025 - 31 Juillet 2025',
        type: "Stage",
        detail: " "
    },
    // {
    //     id: 2,
    //     role: 'backend Developper',
    //     company: 'Coca-cola',
    //     date: 'Mar 2022 - Sep 2023'
    // }
]
</script>

<template>
    <section class="text-white py-20 relative overflow-hidden" id="skills">
        <div class="max-w-7xl mx-auto px-6 lg:px-16 relative z-10 flex flex-col gap-20">
            
            <!-- SECTION SKILLS (Plein écran / Grid de catégories) -->
            <div data-aos="fade-right" class="w-full">
                <h2 class="text-4xl md:text-5xl font-extrabold mb-12">Technical <span class="text-primary">Skills</span></h2>
                
                <!-- Grid pour afficher les catégories de compétences côte à côte sur grand écran -->
                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <div v-for="[categorie, ...competences] in skills" :key="categorie" class="group bg-[#111a3e]/30 p-6 rounded-2xl border border-[#1f1641]">
                        <h3 class="text-xl font-bold mb-6 text-primary border-b border-gray-800 pb-2">{{ categorie }}</h3>
                        
                        <!-- Liste des compétences de la catégorie avec espacement -->
                        <div class="space-y-6">
                            <div v-for="(skill, index) in competences" :key="skill.id + '-' + index" class="flex flex-col gap-2">
                                
                                <div class="flex flex-row w-full items-center">
                                    <div class="p-2 bg-[#111a3e] rounded-lg group-hover:bg-primary/20 transition-colors duration-300 shrink-0">
                                        <Icon :icon="skill.iconName" class="w-6 h-6" />
                                    </div>
                                    <span class="font-medium tracking-wide ml-3 text-sm">
                                        {{ skill.name }}
                                    </span>
                                    <span class="text-primary font-bold ml-auto text-sm">
                                        {{ skill.width }}
                                    </span>
                                </div>
                                
                                <div class="h-2 w-full bg-[#131d30] rounded-full p-0.5">
                                    <div class="h-full rounded-full bg-linear-to-r from-primary to-green-400 shadow-[0_0_10px_#06a2c2]" :style="{width: skill.width}"></div>
                                </div>

                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- SECTION EXPERIENCE (Juste en bas) -->
            <div v-if="experiences && experiences.length > 0" data-aos="fade-left" class="w-full">
                <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                    Work <span class="text-primary"> Experience</span>
                </h2>
                <div class="grid md:grid-cols-2 gap-6">
                    <div v-for="exp in experiences" :key="exp.id" class="group relative p-6 rounded-2xl bg-[#111a3e] border border-[#1f1641] hover:border-primary/50 transition-all duration-300">
                        <div class="flex gap-4">
                            <div class="shrink-0 mt-1">
                                <div class="p-3 bg-[#050816] rounded-xl border border-gray-800 group-hover:border-primary transition-colors">
                                    <Briefcase class="text-primary" :size="24" />
                                </div>
                            </div>
                            <div class="grow">
                                <h3 class="text-xl font-bold text-white group-hover:text-primary transition-colors">
                                    {{ exp.role }}
                                </h3>
                                <div class="flex flex-col sm:flex-row sm:items-center gap-2 sm:gap-4 text-sm text-gray-400 mt-1">
                                    <span class="flex items-center gap-1.5">
                                        <Building2 :size="14" class="text-primary" />
                                        {{ exp.company }}
                                    </span>
                                    <span class="flex items-center gap-1.5">
                                        <Calendar1 :size="14" class="text-primary" />
                                        {{ exp.date }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>
