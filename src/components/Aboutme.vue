<template>
    <section id="aboutme" class="min-h-screen py-16 text-gray-200 bg-[#0A192F]" v-intersection-observer="onIntersect">
        <div class="container px-4 mx-auto max-w-7xl">
            <!-- About Me Header section remains the same -->
            <div class="mb-16 text-left slide-in-left">
                <h2 class="flex items-center gap-3 mb-6 text-4xl font-bold tracking-tight text-white group">
                    <svg xmlns="http://www.w3.org/2000/svg"
                        class="w-8 h-8 text-[#64FFDA] transition-transform duration-300 group-hover:rotate-12"
                        fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                    </svg>
                    <span class="relative hover-underline-animation">About Me</span>
                </h2>
                <p class="max-w-2xl text-lg leading-relaxed text-gray-400 delay-200 slide-in-left">
                    I'm a passionate developer specializing in creating dynamic and visually engaging web applications,
                    with a focus on transforming ideas into elegant solutions.
                </p>
            </div>

            <div class="grid gap-16 lg:grid-cols-2">
                <!-- Profile Content -->
                <div class="space-y-12 slide-in-left delay-400">
                    <p class="text-lg text-gray-400">
                        Beyond my front-end focus, I draw on experience with back-end and full-stack projects,
                        allowing me to approach challenges from different angles and provide well-rounded solutions.
                        Every line of code is a step toward mastering my craft.
                    </p>

                    <!-- Technologies Section -->
                    <div class="technology-section">
                        <h3 class="mb-8 text-2xl font-semibold text-white hover-underline-animation">Technologies I Work
                            With</h3>
                        <div class="grid grid-cols-2 gap-4 sm:grid-cols-3">
                            <div v-for="(tech, index) in technologies" :key="index" class="tech-card group"
                                :style="{ animationDelay: `${index * 100}ms` }">
                                <div
                                    class="relative p-5 transition-all duration-300 bg-[#112240] rounded-lg group-hover:bg-[#1A2C4E] border border-transparent group-hover:border-[#64FFDA]/30">
                                    <!-- Glow effect -->
                                    <div
                                        class="absolute inset-0 transition-opacity duration-300 opacity-0 bg-gradient-to-r from-[#64FFDA]/20 to-transparent rounded-lg blur-xl group-hover:opacity-100">
                                    </div>

                                    <div class="relative flex items-center space-x-3">
                                        <img :src="tech.icon" :alt="tech.name" class="w-6 h-6" />
                                        <h4 class="text-sm font-medium text-gray-300 group-hover:text-[#64FFDA]">{{
                                            tech.name }}</h4>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Platforms Section -->
                    <div class="platform-section">
                        <h3 class="mb-8 text-2xl font-semibold text-white hover-underline-animation">Platforms & Tools
                        </h3>
                        <div class="grid grid-cols-2 gap-4 sm:grid-cols-3">
                            <div v-for="(platform, index) in platforms" :key="index" class="platform-card group"
                                :style="{ animationDelay: `${index * 100}ms` }">
                                <div
                                    class="relative p-5 transition-all duration-300 bg-[#112240] rounded-lg group-hover:bg-[#1A2C4E] border border-transparent group-hover:border-[#64FFDA]/30">
                                    <!-- Glow effect -->
                                    <div
                                        class="absolute inset-0 transition-opacity duration-300 opacity-0 bg-gradient-to-r from-[#64FFDA]/20 to-transparent rounded-lg blur-xl group-hover:opacity-100">
                                    </div>

                                    <div class="relative flex items-center space-x-3">
                                        <img :src="platform.icon" :alt="platform.name" class="w-6 h-6" />
                                        <h4 class="text-sm font-medium text-gray-300 group-hover:text-[#64FFDA]">{{
                                            platform.name }}</h4>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Profile Image Section remains same -->
                <div class="relative max-w-md mx-auto lg:mx-0 slide-in-right">
                    <div class="cursor-pointer profile-container group">
                        <div
                            class="absolute inset-0 transition-transform duration-500 border-2 rounded-lg border-[#64FFDA] translate-x-5 translate-y-5 group-hover:translate-x-2 group-hover:translate-y-2">
                        </div>

                        <div class="relative overflow-hidden rounded-lg profile-wrapper">
                            <img src="../assets/img/profile/we2.jpg" alt="Profile"
                                class="object-cover w-full max-w-md transition-all duration-700 filter grayscale hover:grayscale-0 profile-image" />
                            <div
                                class="absolute inset-0 transition-opacity duration-500 bg-[#64FFDA]/9 group-hover:opacity-0">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AboutMe',
    data() {
        return {
            technologies: [
                { name: 'HTML,CSS,JS ', icon: '/images/htjscs.png' },
                { name: 'C#', icon: '/images/csharp.png' },
                { name: 'JAVA', icon: '/images/java.png' },
                { name: 'PYTHON', icon: '/images/python.png' },
                { name: 'PHP', icon: '/images/php.png' },
                { name: 'Node.js', icon: '/images/nodejs.png' },
                { name: 'Vue.js', icon: '/images/vue.png' },
                { name: 'Nuxt.js', icon: '/images/favicon.ico' },
                { name: 'Asp .Net', icon: '/images/asp.png' },
            ],
            platforms: [
                { name: 'GitHub', icon: '/images/github.png' },
                { name: 'Azure DevOps', icon: '/images/azure.png' },
                { name: 'Opera PMS', icon: '/images/opera1.png' },
                { name: 'Opera EMC', icon: '/images/opr.png' },
                { name: 'Postman', icon: '/images/postman.png' },
                { name: 'SSMS', icon: '/images/sql.png' }
            ],
            isVisible: false
        }
    },
    methods: {
        onIntersect(entries) {
            this.isVisible = entries[0].isIntersecting;
        },
        observeElements() {
            const elements = document.querySelectorAll('.slide-in-left, .slide-in-right, .fade-in');
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        observer.unobserve(entry.target); // Stops observing after animation runs once
                    }
                });
            }, { threshold: 0.3 }); // Trigger when 20% of the element is visible

            elements.forEach(el => observer.observe(el));
        }
    },
    mounted() {
        this.observeElements();
    },
}
</script>

<style scoped>
/* Hover underline animation */
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

/* Enhanced card animations */
.tech-card,
.platform-card {
    animation: fadeUp 0.6s ease-out backwards;
}

@keyframes fadeUp {
    from {
        opacity: 0;
        transform: translateY(20px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Card hover effects */
.tech-card>div,
.platform-card>div {
    position: relative;
    z-index: 1;
    overflow: hidden;
}

.tech-card>div::before,
.platform-card>div::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg,
            transparent,
            rgba(100, 255, 218, 0.05),
            transparent);
    transition: 0.5s;
}

.tech-card:hover>div::before,
.platform-card:hover>div::before {
    left: 100%;
}

/* Section transitions */
.technology-section,
.platform-section {
    opacity: 0;
    transform: translateY(20px);
    animation: sectionFadeIn 0.8s ease-out forwards;
}

.platform-section {
    animation-delay: 200ms;
}

@keyframes sectionFadeIn {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}



/* Profile image hover effects */
.profile-container {
    perspective: 1000px;
}

.profile-wrapper {
    transition: transform 0.6s ease-in-out;
}

.profile-container:hover .profile-wrapper {
    transform: translateX(-8px) translateY(-8px);
}

.profile-image {
    transform: scale(1);
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

.profile-container:hover .profile-image {
    transform: scale(1.05);
}

/* Slide and fade animations */
.slide-in-left {
    opacity: 0;
    transform: translateX(-50px);
    animation: slideInLeft 3s ease forwards;
}

.slide-in-right {
    opacity: 0;
    transform: translateX(50px);
    animation: slideInRight 3s ease forwards;

}

.fade-in {
    opacity: 0;
    animation: fadeIn 3s ease forwards;

}

/* Slide and fade animations */
.slide-in-left,
.slide-in-right,
.fade-in {
    opacity: 0;
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

/* Slide-in from the left */
.slide-in-left {
    transform: translateX(-50px);
}

.slide-in-left.visible {
    opacity: 1;
    transform: translateX(0);
}

/* Slide-in from the right */
.slide-in-right {
    transform: translateX(50px);
}

.slide-in-right.visible {
    opacity: 1;
    transform: translateX(0);
}

/* Fade-in effect */
.fade-in {
    opacity: 0;
}

.fade-in.visible {
    opacity: 1;
}

/* Delay classes */
.delay-200 {
    animation-delay: 200ms;
}

.delay-400 {
    animation-delay: 400ms;
}

/* Smooth scrolling */
html {
    scroll-behavior: smooth;
}

@media (prefers-reduced-motion: reduce) {

    .slide-in-left,
    .slide-in-right,
    .fade-in,
    .profile-wrapper,
    .tech-card {
        animation: none;
        transition: none;
    }

    .hover-underline-animation::after {
        transition: none;
    }
}
</style>