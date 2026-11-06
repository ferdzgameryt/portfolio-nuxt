
<template>
  <div>
    <!-- Navigation Bar -->
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

    <!-- Tech Stack Section -->
    <div class="container2">

      <h1 class="page-title">Tech Stack</h1>

      <div class="grid">

        <div class="card">
          <img src="/img/html.png" alt="HTML">
          <p>HTML</p>
        </div>

        <div class="card">
          <img src="/img/css.png" alt="CSS">
          <p>CSS</p>
        </div>

        <div class="card">
          <img src="/img/git.png" alt="Git">
          <p>Git</p>
        </div>

        <div class="card">
          <img src="/img/github.png" alt="GitHub">
          <p>GitHub</p>
        </div>

        <div class="card">
          <img src="/img/javay.png" alt="Java">
          <p>Java</p>
        </div>

        <div class="card">
          <img src="/img/android.png" alt="Android Studio">
          <p>Android Studio</p>
        </div>

        <div class="card">
          <img src="/img/postgre.png" alt="PostgreSQL">
          <p>PostgreSQL</p>
        </div>

        <div class="card">
          <img src="/img/c.png" alt="C">
          <p>C</p>
        </div>

        <div class="card">
          <img src="/img/vs.png" alt="VS Code">
          <p>VS Code</p>
        </div>

        <div class="card">
          <img src="/img/javascript.png" alt="JavaScript">
          <p>JavaScript</p>
        </div>

      </div>
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

// Close Menu When a Navigation Link is Clicked
const closeMenu = () => {
  isMenuOpen.value = false
}
</script>
