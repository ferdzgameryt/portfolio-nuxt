<script setup>
import { ref } from 'vue'

// Hamburger Menu
const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const url = useRequestURL()


const title = 'Home | Jan Ferdie Almario'
const description =
  'Explore the personal portfolio of Jan Ferdie Almario, featuring his background, technical skills, and certifications as a Bachelor of Science in Information Technology student.'


useHead({
  title,
  link: [{ rel: 'canonical', href: url.href }],
})


useSeoMeta({
  description,
  ogTitle: title,
  ogDescription: description,
  ogType: 'website',
  ogUrl: url.href,
  ogImage: `${url.origin}/img/myface.jpg`, 
  ogImageAlt: 'Jan Ferdie Almario personal portfolio website preview',
})
</script>

<template>
  <div class="home-page">

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

  <NuxtLink
    to="/tech-stack"
    class="btn w-80 h-26 rounded-xl border-2 border-black bg-[#00000099] text-[#f8f8f8] hover:border-white hover:bg-[#244d72] hover:shadow-[0_0_10px_white]"
  >
    TECH STACK
  </NuxtLink>

  <NuxtLink
    to="/about"
    class="btn w-80 h-26 rounded-xl border-2 border-black bg-[#00000099] text-[#f8f8f8] hover:border-white hover:bg-[#244d72] hover:shadow-[0_0_10px_white]"
  >
    ABOUT
  </NuxtLink>

  <NuxtLink
    to="/certificates"
    class="btn w-80 h-26 rounded-xl border-2 border-black bg-[#00000099] text-[#f8f8f8] hover:border-white hover:bg-[#244d72] hover:shadow-[0_0_10px_white]"
  >
    CERTIFICATIONS
  </NuxtLink>

</div>

    </div>
  </div>
</template>
