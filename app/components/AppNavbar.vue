<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

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

      <button
        type="button"
        class="hamburger"
        :class="{ active: isMenuOpen }"
        :aria-expanded="isMenuOpen"
        aria-label="Toggle navigation menu"
        @click="toggleMenu"
      >
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </button>
    </nav>
  </header>
</template>
