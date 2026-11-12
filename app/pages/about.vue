<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
} 

const url = useRequestURL()

const title = 'About Me | Jan Ferdie Almario'
const description =
  'Learn more about Jan Ferdie Almario, a BSIT student passionate about technology, coding, gadget repair, and aspiring to become a computer technician.'


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
})

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

  <div class="container2 about-title">
    <h1 class="page-title">About Me</h1>
  </div>

    <div class="about-page w-full flex justify-center">

        <div class="card w-full max-w-[900px] mx-auto
                    bg-white/5 border-2 border-white
                    rounded-2xl backdrop-blur-md
                    hover:scale-[1.05]
                    transition-transform duration-300">

            <div class="card-body">

                <p class="text-[24px] leading-relaxed text-center font-['Roboto_Slab',serif]">
                    Hi everyone! I'm Ferdz, and I'd like to share a little about myself. My full name is Jan Ferdie Almario. 
                    I'm a motivated and passionate person who always tries to do the things I love. I am currently studying BSIT at St. Dominic College of Asia because I enjoy learning about technology and coding. 
                    I believe that we only live once, so we should make the most out of life. Ever since I was young, I've loved fixing gadgets and learning how to code. I also dream of creating my own games someday, which is why I chose this path.
                </p>

                <p class="text-[24px] leading-relaxed text-center font-['Roboto_Slab',serif]">
                    As an IT student and someone who is taking this path, my professional aspiration is to become a web developer someday. 
                    I want to create websites that can be both functional and useful to everyone. Even though this field is challenging, I believe that with hard work and dedication, I can achieve my goals and continue improving my skills in the IT industry.
                </p>

            </div>

        </div>

    </div>

</template>

