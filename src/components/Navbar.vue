<!-- Navbar.vue -->
<template>
  <nav class="py-4 text-white bg-gradient-to-r from-gray-900 via-purple-900 to-black">
    <div class="container flex items-center justify-between mx-auto">
      <div class="flex items-center">
        <img src="/images/logo.png" alt="Site Logo" class="mr-0 transition-transform duration-700 logo hover:scale-110" />
        <NuxtLink to="/" class="text-2xl font-bold transition-transform duration-700 hover:scale-110">CJAY</NuxtLink>
      </div>
      <!-- Navigation Links -->
      <ul class="hidden space-x-6 md:flex">
        <li>
          <a href="#home" class="flex items-center space-x-2 transition-transform duration-700 hover:text-yellow-200 logo hover:scale-110">
            <i class="fas fa-home"></i>
            <span>Home</span>
          </a>
        </li>
        <li>
          <a href="#projects" class="flex items-center space-x-2 transition-transform duration-700 hover:text-yellow-200 hover:scale-110">
            <i class="fas fa-folder-open"></i>
            <span>Projects</span>
          </a>
        </li>
        <li>
          <a href="#contact" class="flex items-center space-x-2 transition-transform duration-700 hover:text-yellow-200 hover:scale-110">
            <i class="fas fa-envelope"></i>
            <span>Contact</span>
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>



<script>
export default {
  mounted() {
    // Load Font Awesome if not already loaded
    if (!document.querySelector('link[href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"]')) {
      const link = document.createElement('link');
      link.rel = 'stylesheet';
      link.href = 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css';
      document.head.appendChild(link);
    }
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Protest+Guerrilla&family=Righteous&family=SUSE:wght@100..800&family=Space+Grotesk:wght@300..700&display=swap');
.logo {
  width: 70px; /* Adjust width as needed */
  height: auto; /* Keep aspect ratio */
}

nuxtlink {
  /* font-family: "Space Grotesk", sans-serif; */
  font-family: "Righteous", sans-serif;

}
</style>
