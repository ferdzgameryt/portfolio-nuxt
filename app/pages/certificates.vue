
<script setup lang="ts">
import { ref } from 'vue'

// Image Modal
const isModalOpen = ref(false)
const selectedImage = ref('')

const openModal = (imageSrc: string) => {
  selectedImage.value = imageSrc
  isModalOpen.value = true
}

const closeModal = () => {
  isModalOpen.value = false
  selectedImage.value = ''
}

const url = useRequestURL()


const title = 'Certifications | Jan Ferdie Almario'
const description =
  'Certifications earned by Jan Ferdie Almario: Word Associate, PowerPoint Associate'


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
  ogImage: `${url.origin}/img/powerpoint.jpg`, 
  ogImageAlt: 'Microsoft Office Specialist Word Associate badge',
})
</script>

<template>
  <div>
    <AppNavbar />

    <!-- Certifications Title -->

  <div class="container2">
    <h1 class="page-title">Certifications</h1>
  </div>
    <!-- Certification Cards -->
    <div class="flex flex-wrap justify-center gap-10">

      <!-- Microsoft Word -->
      <div
        class="w-full sm:w-1/2 md:w-1/3 lg:w-1/4 p-4 aspect-4/3 text-center
        bg-[#061d31] rounded-lg shadow-3xl shadow-[#1e2948]
        mx-6 -mt-5 mb-18 hover:scale-105"
      >
        <img
          src="/img/word.jpg"
          alt="Microsoft Word Certification"
          class="rounded-lg cursor-pointer"
          @click="openModal('/img/word.jpg')"
        />

        <p class="block font-bold text-white-100 pt-2 mbe-3 m-2 text-2xl">
          Microsoft Office Specialist:
          <br />
          Word
          <br />
          Associate
        </p>

        <a
          href="https://www.certiport.com/portal/pages/credentialverification.aspx"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-3 px-4 py-2 bg-[#23649d] text-white font-semibold
          rounded-l hover:bg-[#18354E] transition"
        >
          Verify Certification
        </a>
      </div>

      <!-- Microsoft PowerPoint -->
      <div
        class="w-full sm:w-1/2 md:w-1/3 lg:w-1/4 p-4 text-center
        bg-[#061d31] rounded-lg mx-6 -mt-5 mb-18 hover:scale-105"
      >
        <img
          src="/img/powerpoint.jpg"
          alt="Microsoft PowerPoint Certification"
          class="rounded-lg cursor-pointer"
          @click="openModal('/img/powerpoint.jpg')"
        />

        <p class="block font-bold text-white-100 pt-2 mbe-3 m-2 text-2xl">
          Microsoft Office Specialist:
          <br />
          PowerPoint
          <br />
          Associate
        </p>

        <a
          href="https://www.certiport.com/portal/pages/credentialverification.aspx"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-3 px-4 py-2 bg-[#23649d] text-white font-semibold
          rounded-lg hover:bg-[#18354E] transition"
        >
          Verify Certification
        </a>
      </div>

    </div>

    <!-- Image Modal -->
    <div
      v-if="isModalOpen"
      class="fixed inset-0 bg-black/80 flex items-center justify-center z-50"
      @click="closeModal"
    >
      <img
        :src="selectedImage"
        alt="Certification Preview"
        class="max-w-[90%] max-h-[90%] rounded shadow-lg"
        @click.stop
      />
    </div>

  </div>
</template>


