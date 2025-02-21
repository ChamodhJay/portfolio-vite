<template>
    <section id="projects" class="py-16 bg-gradient-to-r from-gray-900 via-purple-900 to-black">
        <div class="container px-4 mx-auto">
            <div class="mb-16 text-left slide-in-left">
                <h2 class="flex items-center gap-3 mb-6 text-4xl font-bold tracking-tight text-white group">
                    <i class="fa fa-cog" style="color: aquamarine;" aria-hidden="true"></i>
                    <span class="relative hover-underline-animation">Current Projects</span>
                </h2>
            </div>

            <div class="grid grid-cols-1 gap-6 sm:gap-8 sm:grid-cols-2 lg:grid-cols-3 w-full sm:w-[90%] mx-auto">
                <div v-for="(project, index) in projects" 
                     :key="project.id"
                     :ref="el => projectRefs[index] = el"
                     class="project-card"
                     :style="{
                         transitionDelay: `${isMobile ? 0 : index * 100}ms`
                     }"
                     :class="{
                         'appear': project.isVisible,
                         'mobile': isMobile
                     }"
                >
                    <NuxtLink :to="project.link" :target="'_blank'" class="block">
                        <div class="relative overflow-hidden rounded-t-lg">
                            <img :src="project.image" :alt="project.title"
                                class="object-cover w-full h-48 transition-transform duration-500 ease-in-out transform hover:scale-110" />
                            <div class="absolute inset-0 transition-opacity opacity-0 bg-black/20 hover:opacity-100"></div>
                        </div>
                    </NuxtLink>

                    <div class="p-6">
                        <h3 class="mb-4 text-xl font-bold text-white sm:text-2xl">{{ project.title }}</h3>

                        <div class="flex flex-wrap gap-1 mt-4 mb-3">
                            <span v-for="tech in project.technologies" :key="tech"
                                class="px-3 py-1 text-xs font-normal text-white transition duration-300 bg-transparent border border-purple-500 rounded-full hover:bg-purple-500/20 hover:shadow-md hover:shadow-purple-500/50">
                                {{ tech }}
                            </span>
                        </div>

                        <div v-if="project.description.length > 200">
                            <p v-if="!project.isExpanded" class="text-gray-300 text-balance">
                                {{ project.description.substring(0, 100) + '...' }}</p>
                            <p v-else class="text-gray-300 text-balance">{{ project.description }}</p>
                            <button @click="toggleDescription(project)"
                                class="text-purple-400 transition duration-200 hover:text-purple-300 hover:underline">
                                {{ project.isExpanded ? 'See Less' : 'See More' }}
                            </button>
                        </div>
                        <div v-else>
                            <p class="text-gray-300">{{ project.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';



const projects = ref([{
            id: 1,
            title: 'VBA MACRO SHEET GENERATOR',
            description: 'This is a custom-built VBA macro designed to automate the processing of large hotel reports within Excel. The macro streamlines data manipulation by automating tasks such as data cleansing, aggregation, and formatting, significantly reducing manual workload. It also performs advanced calculations and generates detailed summary reports, enabling hotel management to derive actionable insights with greater accuracy and speed. The solution enhances operational efficiency and improves decision-making through streamlined reporting workflows.',
            image: '/images/project/vbamacro.png',
     link: '',
     technologies: ["Visual Basic"],
            isExpanded: false
        },
        {
            id: 2,
            title: 'RESERVATION UPLOADER CLI PROGRAMME',
            description: 'This is a Node.js-based application developed to automate the uploading of guest reservation data into Opera Cloud via the Oracle Hospitality API. The tool imports reservation details from CSV files and includes robust validation mechanisms to ensure data integrity. Guest profile IDs are cross-checked for validity, and any missing or invalid entries trigger detailed error notifications, allowing for quick resolution. The tool significantly reduces manual data entry errors and optimizes the reservation management process, improving operational efficiency for hotels.',
            image: '/images/project/cli.jpeg',
            link: '',
            technologies: ["Node js"],
            isExpanded: false
        },
        {
            id: 3,
            title: 'AFFERO SELF CHECK-IN WEB SYSTEM',
            description: 'This is a comprehensive self-check-in system, incorporating both a backend notification service and a frontend pre-arrival web portal AscNotifier: A Windows service developed using C# .NET, designed to automate pre-arrival email notifications for hotel guests. The service runs daily, checking upcoming reservations and sending personalized reminder emails three days prior to guests arrival This feature ensures timely communication  enhancing the guest experience and improving hotel operations.Affero Pre-arrival Web Portal: A web-based application built with Nuxt.js, providing guests with a seamless pre-arrival check-in process. The portal allows users to manage their reservations and complete check-in tasks online, improving convenience and reducing on-site check-in times. Integrated with AscNotifier this system provides a unified efficient guest interaction platform. ',
            image: '/images/project/reservation.jpeg',
            link: '',
            technologies: ["Vue.js", "Nuxt.js","Tailwind"],
            isExpanded: false
        }
    ]);

const projectRefs = ref([]);
const isMobile = ref(false);

function toggleDescription(project) {
    project.isExpanded = !project.isExpanded;
}

function checkMobile() {
    isMobile.value = window.innerWidth < 768;
}

onMounted(() => {
    // Check initial mobile state
    checkMobile();
    
    // Add resize listener
    window.addEventListener('resize', checkMobile);

    const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
            if (entry.isIntersecting) {
                const index = projectRefs.value.findIndex(ref => ref === entry.target);
                if (index !== -1) {
                    projects.value[index].isVisible = true;
                }
            }
        });
    }, {
        threshold: isMobile.value ? 0.1 : 0.2,
        rootMargin: isMobile.value ? '0px' : '50px'
    });

    // Small delay to ensure refs are ready
    setTimeout(() => {
        projectRefs.value.forEach((el) => {
            if (el) observer.observe(el);
        });
    }, 100);

    // Cleanup
    return () => {
        window.removeEventListener('resize', checkMobile);
    };
});
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Protest+Guerrilla&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=SUSE:wght@100..800&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=SUSE:wght@100..800&family=Space+Grotesk:wght@300..700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=Righteous&family=SUSE:wght@100..800&family=Space+Grotesk:wght@300..700&display=swap');

html {
    scroll-behavior: smooth;
}

h1 {
    font-family: "Protest Guerrilla", sans-serif;
}

h2,
span,
a {
    font-family: "Righteous", sans-serif;
}

h3,
p {
    font-family: "Space Grotesk", sans-serif;
}

/* Project card animations */
.project-card {
    position: relative;
    opacity: 0;
    transform: translateY(30px);
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: hidden;
    border: 1px solid transparent;
    border-radius: 0.5rem;
    background-color: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(8px);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    will-change: transform, opacity;
}

.project-card.appear {
    opacity: 1;
    transform: translateY(0);
}

/* Mobile-specific styles */
.project-card.mobile {
    transition: all 0.3s ease-out;
}

.project-card.mobile.appear {
    transform: translateY(0);
}

/* Hover effects - disabled on mobile */
@media (min-width: 768px) {
    .project-card:hover {
        transform: translateY(-10px) scale(1.02);
        box-shadow: 0 10px 30px -10px rgba(139, 92, 246, 0.5);
        border-color: rgb(139, 92, 246);
    }
}

/* Mobile hover effects */
@media (max-width: 767px) {
    .project-card:active {
        transform: scale(0.98);
        transition: transform 0.2s;
    }
}

.hover-underline-animation {
    display: inline-block;
    position: relative;
}

.hover-underline-animation::after {
    content: '';
    position: absolute;
    width: 0;
    height: 2px;
    bottom: -4px;
    left: 0;
    background-color: #64FFDA;
    transition: width 0.3s ease-in-out;
}

.hover-underline-animation:hover::after {
    width: 100%;
}
</style>