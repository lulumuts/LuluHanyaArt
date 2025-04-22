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
body {
  margin: 0;
}

.body{
  display: block;
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
}

.shape1 {
  position: absolute;
  top: 42%;
  left: 70%;
  width: 25rem;
  height: 25rem;
  background: rgb(185, 247, 204);
  border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  filter: blur(6rem);
  animation: shape1 8s infinite;
}

@keyframes shape1 {
  0% {
    transform: translate(0, 0);
    border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  }
  25% {
    transform: translate(-55%, -10%);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
    height: 50rem;
    width: 80rem;
  }
  50% {
    transform: translate(-90%, -10%);
    border-radius: 60% 40% 0% 100% / 1% 74% 26% 99%;
  }
  75% {
    transform: translate(-30%, -10%);
    border-radius: 0% 100% 100% 0% / 0% 100% 100% 0%;
    height: 30rem;
    width: 45rem;
  }
  100% {
    transform: translate(0%, 0%);
    border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  }
}

.shape2 {
  position: absolute;
  top: 33%;
  left: 40%;
  width: 35rem;
  height: 25rem;
  background: rgb(185, 247, 204);
  border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  filter: blur(12rem);
  animation: shape2 35s infinite;
}

@keyframes shape2 {
  0% {
    transform: translate(0, 0);
    border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  }
  25% {
    transform: translate(-55%, -55%);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
    height: 50rem;
    width: 50rem;
  }
  50% {
    transform: translate(-70%, -70%);
    border-radius: 60% 40% 0% 100% / 1% 74% 26% 99%;
  }
  75% {
    transform: translate(-30%, -30%);
    border-radius: 0% 100% 100% 0% / 0% 100% 100% 0%;
  }
  100% {
    transform: translate(0%, 0%);
    border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  }
}

.shape3 {
  position: absolute;
  top: 20%;
  left: 80%;
  width: 25rem;
  height: 25rem;
  background: rgb(252, 255, 192);
  border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  filter: blur(14rem);
  animation: shape3 35s infinite;
}

@keyframes shape3 {
  0% {
    transform: translate(0, 0);
    border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  }
  25% {
    transform: translate(-125%, -25%);
    border-radius: 28% 72% 81% 19% / 78% 25% 75% 22%;
    height: 50rem;
    width: 50rem;
  }
  50% {
    transform: translate(-90%, -35%);
    border-radius: 60% 40% 0% 100% / 1% 74% 26% 99%;
  }
  75% {
    transform: translate(-30%, -40%);
    border-radius: 0% 100% 100% 0% / 0% 100% 100% 0%;
  }
  100% {
    transform: translate(0%, 0%);
    border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  }
}

.shape4 {
  position: absolute;
  top: 42%;
  left: 70%;
  width: 25rem;
  height: 25rem;
  background: rgb(247, 247, 203);
  border-radius: 24% 76% 77% 23% / 30% 30% 70% 70%;
  filter: blur(3rem);
  animation: shape1 20s infinite;
}

.shape5 {
  position: absolute;
  top: 33%;
  left: 40%;
  width: 35rem;
  height: 25rem;
  background: rgb(249, 254, 194);
  border-radius: 73% 27% 77% 23% / 53% 4% 96% 47%;
  filter: blur(5rem);
  animation: shape2 15s infinite;
}

.shape6 {
  position: absolute;
  top: 20%;
  left: 80%;
  width: 25rem;
  height: 25rem;
  background: rgb(247, 255, 204);
  border-radius: 70% 30% 80% 20% / 42% 25% 75% 58%;
  filter: blur(5rem);
  animation: shape3 15s infinite;
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
