
<template>
  <header>
    <nav class="navbar">
      <h1 class="logo">JFA</h1>
    </nav>
  </header>

  <div class="container">

    <div class="top">
      <img src="/img/myface.jpg" class="profile" alt="Jan Ferdie Almario">

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
</script>
