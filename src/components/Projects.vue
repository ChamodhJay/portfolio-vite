<template>
    <section id="projects" class="py-16 bg-gradient-to-r from-gray-900 via-purple-950 to-black">
        <div class="container px-4 mx-auto">
            <div class="mb-16 text-left slide-in-left">
                <h2 class="flex items-center gap-3 mb-6 text-4xl font-bold tracking-tight text-white group">
                    <i class="fa fa-folder-open" style="color: aquamarine;" aria-hidden="true"></i>
                    <span class="relative hover-underline-animation">Projects</span>
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
                        <div class="relative overflow-hidden rounded-t-lg cursor-pointer ">
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
    title: 'EMPLOYEE LEAVE MANAGEMENT SYSTEM',
    description: 'Pulathisi Leave Management System is a web-based application designed to streamline the process of managing employee leaves within an organization. Developed using PHP, HTML, CSS, JavaScript, and Bootstrap, this system offers an intuitive interface for employees and administrators to handle leave requests, approvals, and records efficiently.',
    image: '/images/pulathisi.png',
    link: 'https://github.com/ChamodhJay/Employee-Leave-Management-System-PHP',
    technologies: ["HTML", "CSS","PHP"],
    isExpanded: false,
    isVisible: false
},
{
    id: 2,
    title: 'YOUTUBE VIDEO DOWNLOADER',
    description: 'This project is a simple YouTube Video Downloader built with Python, using Tkinter for the graphical interface. It allows users to download videos from YouTube by pasting the video URL, selecting the preferred video quality and format, and clicking "Download." The app supports multiple formats and resolutions, providing a smooth user experience with a real-time download progress bar. It also handles errors effectively, ensuring ease of use.',
    image: '/images/project/youtube.png',
    link: 'https://github.com/ChamodhJay/Youtube_Video_Downloader_Python-Project',
    technologies: ["Python","Tkinter"],
    isExpanded: false,
    isVisible: false
},
{
    id: 3,
    title: 'INVENTORY MANAGEMENT SYSTEM',
    description: 'This project is an Inventory Management System developed in Java to help manage and track inventory efficiently. It allows users to add, update, delete, and search for products in the inventory. The system keeps detailed records of stock levels, product details, and inventory history. It includes features such as real-time stock updates, automated alerts for low stock, and comprehensive reporting capabilities. The system is designed for scalability and ease of use, making it suitable for small to medium-sized businesses.',
    image: '/images/project/ims.png',
    link: 'https://github.com/ChamodhJay/Inventory-Management-System-IMS--JAVA',
    technologies: ["JAVA"],
    isExpanded: false,
    isVisible: false
},
{
    id: 4,
    title: 'FACEBOOK CLONE REACT',
    description: 'This FB Clone Web Application, built using the React framework, delivers a streamlined and dynamic user experience, mimicking the core functionalities of the original Facebook platform. This demo version is designed to showcase the seamless integration of modern front-end technologies, offering users a responsive, efficient, and interactive interface.',
    image: '/images/project/fbclone.png',
    link: 'https://github.com/ChamodhJay/React-Facebook-Clone-Demo',
    technologies: ["React"],
    isExpanded: false,
    isVisible: false
}]);

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