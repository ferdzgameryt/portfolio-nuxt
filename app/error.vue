
<template>
  <div class="error-page">
    <div class="error-content">
      <h1 class="logo">JFA</h1>

      <h2 class="error-code">{{ error.statusCode }}</h2>

      <h1 class="error-title">
        {{ error.statusCode === 404
          ? 'PAGE NOT FOUND'
          : 'OOPS! SOMETHING WENT WRONG' }}
      </h1>

      <p class="error-message">
        {{ error.statusCode === 404
          ? "The page you're looking for doesn't exist or may have been moved."
          : "Sorry, something unexpected happened. Please try again." }}
      </p>

      <button class="home-button" @click="goHome">
        BACK TO HOME
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  error: {
    type: Object,
    required: true
  }
})

const goHome = () => {
  clearError({ redirect: '/' })
}
</script>

<style scoped>
.error-page {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background: #18354E;
  color: #f5f5f5;
  font-family: "Archivo Black", sans-serif;
  text-align: center;
}

.error-content {
  width: 100%;
  max-width: 650px;
  padding: 50px 30px;
  background: rgba(0, 0, 0, 0.35);
  border: 3px solid white;
  border-radius: 15px;
  transition: 0.3s ease;
}

.error-content:hover {
  transform: scale(1.02);
  box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
}

.logo {
  font-size: 30px;
  margin: 0 0 25px;
}

.error-code {
  font-size: 110px;
  margin: 0;
  line-height: 1.2;
}

.error-title {
  font-size: 28px;
  margin: 15px 0;
}

.error-message {
  font-family: "Roboto Slab", serif;
  font-size: 17px;
  line-height: 1.7;
  margin: 20px 0 30px;
}

.home-button {
  padding: 15px 30px;
  background: #061d31;
  color: white;
  border: 2px solid white;
  border-radius: 8px;
  font-family: "Archivo Black", sans-serif;
  font-size: 15px;
  cursor: pointer;
  transition: 0.3s ease;
}

.home-button:hover {
  background: #244d72;
  transform: scale(1.05);
}

@media (max-width: 600px) {
  .error-content {
    padding: 35px 20px;
  }

  .error-code {
    font-size: 80px;
  }

  .error-title {
    font-size: 21px;
  }

  .error-message {
    font-size: 15px;
  }
}
</style>
