<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template class="body">

    <div class="animation-container">
      <div class="shape1"></div>
      <div class="shape2"></div>
      <div class="shape3"></div>
      <div class="shape4"></div>
      <div class="shape5"></div>
      <div class="shape6"></div>
    </div>

  <RouterView />
</template>

<style scoped>
* {
  overflow-x: hidden !important;
}

html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden !important;
  max-width: 100vw;
  width: 100%;
}

.body{
  display: block;
  overflow-x: hidden !important;
  max-width: 100vw;
  width: 100%;
}

h1{
  color: #000;
}

.animation-container {
  background: transparent;
  position: fixed;
  z-index: -1;
  height: 100%;
  width: 100%;
  max-width: 100vw;
  overflow: hidden;
  left: 0;
  right: 0;
}

.shape1 {
  position: absolute;
  top: 42%;
  left: 70%;
  width: 20rem;
  height: 20rem;
  background: rgba(185, 247, 204, 0.3);
  border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  filter: blur(4rem);
  animation: shape1 40s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.4;
}

@keyframes shape1 {
  0% {
    transform: translate(0, 0) scale(1);
    border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  }
  50% {
    transform: translate(-10%, -5%) scale(1.05);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
  }
  100% {
    transform: translate(0%, 0%) scale(1);
    border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  }
}

.shape2 {
  position: absolute;
  top: 33%;
  left: 40%;
  width: 25rem;
  height: 20rem;
  background: rgba(185, 247, 204, 0.2);
  border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  filter: blur(6rem);
  animation: shape2 50s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.3;
}

@keyframes shape2 {
  0% {
    transform: translate(0, 0) scale(1);
    border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  }
  50% {
    transform: translate(-8%, -8%) scale(1.1);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
  }
  100% {
    transform: translate(0%, 0%) scale(1);
    border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  }
}

.shape3 {
  position: absolute;
  top: 20%;
  left: 60%;
  width: 18rem;
  height: 18rem;
  background: rgba(252, 255, 192, 0.25);
  border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  filter: blur(5rem);
  animation: shape3 45s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.3;
}

@keyframes shape3 {
  0% {
    transform: translate(0, 0) scale(1);
    border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  }
  50% {
    transform: translate(-12%, -8%) scale(1.08);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
  }
  100% {
    transform: translate(0%, 0%) scale(1);
    border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  }
}

.shape4 {
  position: absolute;
  top: 42%;
  left: 70%;
  width: 20rem;
  height: 20rem;
  background: rgba(247, 247, 203, 0.2);
  border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  filter: blur(2rem);
  animation: shape1 60s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.2;
}

.shape5 {
  position: absolute;
  top: 33%;
  left: 40%;
  width: 25rem;
  height: 20rem;
  background: rgba(249, 254, 194, 0.15);
  border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  filter: blur(3rem);
  animation: shape2 70s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.2;
}

.shape6 {
  position: absolute;
  top: 20%;
  left: 60%;
  width: 18rem;
  height: 18rem;
  background: rgba(247, 255, 204, 0.2);
  border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  filter: blur(2rem);
  animation: shape3 80s ease-in-out infinite;
  max-width: 100vw;
  overflow: hidden;
  opacity: 0.2;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  /* header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  } */

  .logo {
    margin: 0 2rem 0 0;
  }

  /* header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  } */
/* 
  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  } */
}
</style>
