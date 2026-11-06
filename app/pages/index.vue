
<template>
  <header>
    <nav class="navbar">
      <h1 class="logo">JFA</h1>

      <ul class="nav-menu" :class="{ active: isMenuOpen }">
        <li class="nav-item">
          <NuxtLink to="/" class="nav-link" @click="closeMenu">
            Home
          </NuxtLink>
        </li>

        <li class="nav-item">
          <NuxtLink to="/about" class="nav-link" @click="closeMenu">
            About
          </NuxtLink>
        </li>

        <li class="nav-item">
          <NuxtLink to="/tech-stack" class="nav-link" @click="closeMenu">
            Tech Stack
          </NuxtLink>
        </li>

        <li class="nav-item">
          <NuxtLink to="/certificates" class="nav-link" @click="closeMenu">
            Certifications
          </NuxtLink>
        </li>
      </ul>
      <!-- Hamburger Menu -->
      <div
        class="hamburger"
        :class="{ active: isMenuOpen }"
        @click="toggleMenu"
      >
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </nav>
  </header>

  <div class="container">

    <div class="top">
      <img
        src="/img/myface.jpg"
        class="profile"
        alt="Jan Ferdie Almario"
      >

      <div class="info">
        <h1>Jan Ferdie Almario</h1>
        <p>Frontend Developer</p>
      </div>
    </div>

    <div class="bottom">

      <RouterLink to="/tech-stack" class="box">
        TECH STACK
      </RouterLink>

      <RouterLink to="/about" class="box">
        ABOUT
      </RouterLink>

      <RouterLink to="/certificates" class="box">
        CERTIFICATIONS
      </RouterLink>

    </div>

  </div>
</template>

<script setup>
import { ref } from 'vue'

// Hamburger Menu
const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>
