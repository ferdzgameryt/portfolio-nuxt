
<template>
  <header>
    <nav class="navbar">
      <h1 class="logo">JFA</h1>

      <ul class="nav-menu">
        <li class="nav-item">
          <a href="/" class="nav-link">Home</a>
        </li>

        <li class="nav-item">
          <a href="/about" class="nav-link">About</a>
        </li>

        <li class="nav-item">
          <a href="/tech-stack" class="nav-link">Tech Stack</a>
        </li>

        <li class="nav-item">
          <a href="/certification" class="nav-link">
            Certifications
          </a>
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

  <div class="container2">
    <h1>About Me</h1>

    <div class="about-page">
      <div class="about-text">
        <p>
          Hi everyone! I'm Ferdz, and I'd like to share a little
          about myself. My full name is Jan Ferdie Almario.
          I'm a motivated and passionate person who always tries
          to do the things I love. I am currently studying BSIT
          at St. Dominic College of Asia because I enjoy learning
          about technology and coding.

          I believe that we only live once, so we should make
          the most out of life. Ever since I was young, I've
          loved fixing gadgets and learning how to code.
          I also dream of creating my own games someday,
          which is why I chose this path.
        </p>

        <p>
          As an IT student and someone who is taking this path,
          my professional aspiration is to become a web developer
          someday. I want to create websites that can be both
          functional and useful to everyone. Even though this
          field is challenging, I believe that with hard work
          and dedication, I can achieve my goals and continue
          improving my skills in the IT industry.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>
