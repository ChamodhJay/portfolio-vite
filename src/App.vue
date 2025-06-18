<template>
  <div>
    <Navbar />

    <section
      id="home"
      class="min-h-screen px-6 bg-gradient-to-r from-gray-900 via-purple-900 to-black sm:px-8 lg:px-12"
    >
      <div class="container flex items-center min-h-screen mx-auto">
        <div
          class="flex flex-col items-center justify-between w-full lg:flex-row"
        >
          <!-- Left Content -->
          <div class="w-full space-y-6 text-white lg:w-1/2 lg:pr-12">
            <h1 class="text-4xl font-bold sm:text-5xl lg:text-6xl">
              <span class="text-yellow-400 text-7xl lg:text-8xl drop-shadow-lg"
                >H</span
              >ello, I'm
              <br />
              <span class="text-yellow-400 text-7xl lg:text-8xl drop-shadow-lg"
                >C</span
              >hamodh
              <span class="text-yellow-400 text-7xl lg:text-8xl drop-shadow-lg"
                >J</span
              >ayasinghe
            </h1>

            <div class="relative">
              <p
                class="text-2xl font-bold text-yellow-400 lg:text-3xl typewriter"
              >
                Full Stack Developer
              </p>
            </div>

            <p class="text-lg text-gray-100">
              Passionate about creating elegant solutions through code.
              Specialized in building modern web applications with cutting-edge
              technologies.
            </p>

            <div class="flex space-x-4">
              <a
                href="#aboutme"
                class="relative px-6 py-2 font-bold text-white backdrop-blur-md bg-white/10 border border-1 rounded-lg transition-all duration-300 ease-in-out before:absolute before:inset-0 before:-z-10 before:rounded-lg before:bg-gradient-to-r before:from-blue-600 before:via-purple-600 before:to-black before:bg-[length:400%_400%] before:blur-md before:opacity-50 before:transition-opacity before:duration-300 hover:before:opacity-100 hover:scale-105 hover:border-purple-500"
              >
                About Me
              </a>

              <!-- Social Icons -->
              <!-- <div class="flex items-center space-x-4">
                <a href="#" class="text-white transition-colors hover:text-yellow-400">
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path
                      d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 16h-2v-6h2v6zm-1-6.891c-.607 0-1.1-.496-1.1-1.109 0-.612.492-1.109 1.1-1.109s1.1.497 1.1 1.109c0 .613-.493 1.109-1.1 1.109zm8 6.891h-1.998v-2.861c0-1.881-2.002-1.722-2.002 0v2.861h-2v-6h2v1.093c.872-1.616 4-1.736 4 1.548v3.359z" />
                  </svg>
                </a>
                <a href="#" class="text-white transition-colors hover:text-yellow-400">
                  <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path
                      d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" />
                  </svg>
                </a>
              </div> -->
            </div>
          </div>

          <!-- Right Profile Picture -->
          <div class="flex justify-center w-full mt-12 lg:w-1/2 lg:mt-0">
            <div class="relative">
              <!-- Glow Effect -->

              <div
                class="absolute inset-0 rounded-full bg-gradient-to-r from-[#FF1493] to-[#00FFFF] opacity-80 blur-3xl animate-slideInLeft"
              ></div>

              <div class="image-container">
                <div class="animated-image"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <Aboutme />

    <Experience />

    <projects />

    <Currentprojects />

    <!-- Contact Section -->
    <section
      id="contact"
      class="py-8 text-white bg-gradient-to-r from-gray-800 via-gray-900 to-black md:py-16"
    >
      <div class="container px-4 mx-auto text-center">
        <h2 class="mb-4 text-3xl font-bold md:mb-8 md:text-4xl">
          Get in Touch
        </h2>
        <p class="mb-6 text-lg md:mb-8 md:text-xl">
          Feel free to reach out to me via email or on social media!
        </p>

        <!-- Button Container -->
        <div
          class="flex flex-col items-center justify-center space-y-4 sm:flex-row sm:space-y-0 sm:space-x-4"
        >
          <!-- Email Button -->
          <a
            href="mailto:nimeshacchamodh123@gmail.com"
            target="_blank"
            class="flex items-center justify-center w-full px-4 py-2 space-x-2 text-sm transition-all bg-blue-500 rounded-full hover:scale-105 sm:w-auto md:px-6 md:py-3 hover:bg-blue-600 md:text-base"
          >
            <i class="fas fa-envelope"></i>
            <span>Email Me</span>
          </a>

          <!-- LinkedIn Button -->
          <a
            href="https://www.linkedin.com/in/chamodh-jayasinghe-b27679278/"
            target="_blank"
            class="flex items-center justify-center w-full px-4 py-2 space-x-2 text-sm transition-all bg-green-500 rounded-full hover:scale-105 sm:w-auto md:px-6 md:py-3 hover:bg-green-600 md:text-base"
          >
            <i class="fab fa-linkedin"></i>
            <span>LinkedIn</span>
          </a>

          <!-- GitHub Button -->
          <a
            href="https://github.com/ChamodhJay"
            target="_blank"
            class="flex items-center justify-center w-full px-4 py-2 space-x-2 text-sm transition-all bg-gray-500 rounded-full hover:scale-105 sm:w-auto md:px-6 md:py-3 hover:bg-gray-600 md:text-base"
          >
            <i class="fab fa-github"></i>
            <span>GitHub</span>
          </a>

          <!-- CV Download Button -->
          <a
            href="https://drive.usercontent.google.com/download?id=1A3MOkzLNha4FrWKIDiBNPsP8sggy5irg&export=download&authuser=0&confirm=t&uuid=c23a3370-79f8-45f8-8687-be125816c58d&at=APvzH3qNBWqgt3de9frbDIIxo4_V:1734250307935"
            download
            class="flex items-center justify-center w-full px-4 py-2 space-x-2 text-sm transition-all bg-red-500 rounded-full hover:scale-105 sm:w-auto md:px-6 md:py-3 hover:bg-red-600 md:text-base"
          >
            <i class="fas fa-file-download"></i>
            <span>Download CV</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer
      class="py-4 text-center text-white bg-gradient-to-r from-gray-800 via-gray-900 to-black md:py-6"
    >
      <div class="flex items-center justify-center px-4 space-x-2">
        <img src="/images/logo.png" alt="Site Logo" class="w-auto h-6 md:h-8" />
        <p class="text-sm md:text-base">
          © 2025 CjaySolutions. All rights reserved.
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import Navbar from "./components/Navbar.vue";
import Projects from "./components/Projects.vue";
import Currentprojects from "./components/Ongoingprojects.vue";
import Aboutme from "./components/Aboutme.vue";
import Experience from "./components/Experience.vue";

onMounted(() => {
  // Load Font Awesome stylesheet dynamically if not already loaded
  if (
    !document.querySelector(
      'link[href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"]'
    )
  ) {
    const link = document.createElement("link");
    link.rel = "stylesheet";
    link.href =
      "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css";
    document.head.appendChild(link);
  }
});
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Protest+Guerrilla&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=SUSE:wght@100..800&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=SUSE:wght@100..800&family=Space+Grotesk:wght@300..700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=Righteous&family=SUSE:wght@100..800&family=Space+Grotesk:wght@300..700&display=swap");

@keyframes glow {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
.hover\:before\:animate-glow:hover::before {
  animation: glow 6s linear infinite;
}

html {
  scroll-behavior: smooth;
}

h1 {
  font-family: "Protest Guerrilla", sans-serif;
}

h2,
span,
a {
  /* font-family: "Space Grotesk", sans-serif; */
  font-family: "Righteous", sans-serif;
}

h3,
p {
  font-family: "Space Grotesk", sans-serif;
}

/* Image container styling */
.image-container {
  position: relative;
  width: 16rem;
  /* Width equivalent to w-64 */
  height: 16rem;
  /* Height equivalent to h-64 */
  border: 6px solid white;
  border-radius: 50%;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  z-index: 10;
}

@media (min-width: 1024px) {
  /* Larger screen styles (equivalent to lg:w-96, lg:h-96) */
  .image-container {
    width: 28rem;
    height: 28rem;
  }
}

@media (max-width: 720px) {
  /* Larger screen styles (equivalent to lg:w-96, lg:h-96) */
  .image-container {
    width: 20rem;
    height: 20rem;
  }
}

/* Animated image styling */
.animated-image {
  position: absolute;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  animation: changeImage 6s infinite;
  /* Total 6s for cycling through 3 images */
}

/* Keyframes for background image animation */
@keyframes changeImage {
  0% {
    background-image: url("./assets/img/profile/cjay1.jpg");
  }

  33.33% {
    background-image: url("./assets/img/profile/cjay1.jpg");
  }

  66.66% {
    background-image: url("./assets/img/profile/cjay1.jpg");
  }

  100% {
    background-image: url("./assets/img/profile/cjay1.jpg");
  }
}
</style>

<style scoped>
@keyframes slideInLeft {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
.animate-slideInLeft {
  animation: slideInLeft 2s ease-out;
}
/* Typewriter Animation */
.typewriter {
  overflow: hidden;
  border-right: 0.15em solid #ffd700;
  white-space: nowrap;
  margin: 0 auto;
  letter-spacing: 0.15em;
  animation: typing 3.5s steps(40, end) infinite,
    blink-caret 0.75s step-end infinite;
}

@keyframes typing {
  0% {
    width: 0;
  }

  50% {
    width: 100%;
  }

  90% {
    width: 90%;
    /* Pause after typing */
  }

  93% {
    width: 70%;
    /* Pause after typing */
  }

  96% {
    width: 50%;
    /* Pause after typing */
  }

  100% {
    width: 0;
    /* Reset for the next loop */
  }
}

@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }

  50% {
    border-color: #ffd700;
  }
}
</style>

<!-- /* Rotating Ring Animation */

/* Rotating Ring Animation */
.ring-animation {
  border: 8px dashed rgba(255, 255, 255, 0.5);
  border-radius: 50%;
  animation: spin 10s linear infinite;
}

.ring-animation::before {
  content: '';
  position: absolute;
  inset: -18px;
  /* Increase the spacing between profile and yellow ring */
  border: 8px transparent;
  border-top: 8px dashed #FFD700;
  border-right: 8px dashed #FFD700;
  border-radius: 50%;
  animation: spin-reverse 7s linear infinite;
}

.ring-animation::after {
  content: '';
  position: absolute;
  inset: -35px;
  /* Increase the spacing between yellow ring and white ring */
  border: 8px transparent;
  border-top: 8px dashed #FFD700;
  border-left: 8px dashed #FFD700;
  border-radius: 50%;
  animation: spin 12s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

@keyframes spin-reverse {
  0% {
    transform: rotate(360deg);
  }

  100% {
    transform: rotate(0deg);
  }
} -->
