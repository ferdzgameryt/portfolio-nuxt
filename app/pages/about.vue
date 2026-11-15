<script setup>
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
  <div>
    <AppNavbar />
    <main>
      <div class="container2 about-title">
        <h1 class="page-title">About Me</h1>
      </div>
      <AboutContentCard />
    </main>
  </div>
</template>

