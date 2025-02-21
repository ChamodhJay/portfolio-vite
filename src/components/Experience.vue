<template>
        <!-- Experience Section -->
        <section id="experience" class="py-16 bg-gradient-to-r from-gray-900 via-purple-900 to-black">
          <div class="container px-6 mx-auto">
            <div class="mb-16 text-left fade-in">
              <h2 class="flex items-center gap-3 mb-6 text-4xl font-bold tracking-tight text-white group">
                <i class="fa fa-briefcase" style="color: aquamarine;" aria-hidden="true"></i>
                <span class="relative hover-underline-animation">Experience</span>
              </h2>
            </div>
            <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-3">
              <div v-for="(experience, index) in experiences" :key="experience.id"
                class="relative overflow-hidden transition-transform duration-500 ease-in-out transform border border-transparent rounded-lg shadow-lg bg-white/10 backdrop-blur-lg hover:shadow-purple-500/50 hover:scale-110 hover:border-purple-500"
                :class="{'slide-in': true, 'visible': experience.isVisible}">
                <div class="p-6">
                  <h3 class="mb-2 text-2xl font-bold text-white">{{ experience.position }}</h3>
                  <h4 class="font-semibold text-green-400">{{ experience.company }}</h4>
                  <p class="text-gray-400">{{ experience.date }}</p>
                  <div v-if="experience.description.length > 150" class="mt-3">
                    <p v-if="!experience.isExpanded" class="text-gray-300 text-balance">
                      {{ experience.description.substring(0, 100) + '...' }}
                    </p>
                    <p v-else class="text-gray-300">{{ experience.description }}</p>
                    <button @click="toggleDescription(experience)"
                      class="text-purple-400 transition duration-200 hover:text-purple-300 hover:underline">
                      {{ experience.isExpanded ? 'See Less' : 'See More' }}
                    </button>
                  </div>
                  <div v-else>
                    <p class="text-gray-300">{{ experience.description }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </template>
      
      <script setup>
      import { ref, onMounted } from 'vue'
      
      const experiences = ref([
        {
          id: 1,
          company: "Affero Technology Pvt Ltd",
          position: "Associate Software Developer",
          date: "June 2024",
          description:
            "I was promoted to Associate Software Developer after my internship for demonstrating outstanding performance during the training period. Since then, I have been working on multiple projects and have gained significant experience in software development.",
          isExpanded: false,
          isVisible: false
        },
        {
          id: 2,
          company: "Affero Technology Pvt Ltd",
          position: "Trainee Software Developer",
          date: "December 2023",
          description:
            "I have joined Affero Technology as a trainee software developer for a six-month training period. It was an amazing opportunity for me to grow my future career, and I have learned a lot of technologies, such as Opera PMS cloud systems and how to integrate with cloud systems using the Opera REST API. Additionally, during my training period, I developed some tools using Node.js. So, I think it was an amazing opportunity for me to start my software development career.",
          isExpanded: false,
          isVisible: false
        }
      ])
      
      function toggleDescription(experience) {
        experience.isExpanded = !experience.isExpanded
      }
      
      const observeElements = () => {
        const observer = new IntersectionObserver(entries => {
          entries.forEach(entry => {
            const index = experiences.value.findIndex(exp => exp.id == entry.target.dataset.id);
            if (entry.isIntersecting && index !== -1) {
              experiences.value[index].isVisible = true;
              observer.unobserve(entry.target);
            }
          });
        }, { threshold: 0.2 });
      
        document.querySelectorAll('.slide-in').forEach((el, index) => {
          el.dataset.id = experiences.value[index].id;
          observer.observe(el);
        });
      }
      
      onMounted(() => {
        observeElements();
      });
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
      
      /* Slide-in animations */
      @keyframes slideIn {
        from {
          transform: translateY(30px);
          opacity: 0;
        }
        to {
          transform: translateY(0);
          opacity: 1;
        }
      }
      .slide-in {
        opacity: 0;
        transform: translateY(30px);
        transition: opacity 0.6s ease-out, transform 0.6s ease-out;
      }
      .visible {
        opacity: 1;
        transform: translateY(0);
      }
      </style>
      