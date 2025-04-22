<script setup>
import Home from '../components/Home.vue'
</script>

<template>
  <main>
    <h1>Lulu Hanya Art</h1>
    <div class="marquee">
      <p>Painter. Designer. Coder</p>
    </div>
    <Home />
  </main>
</template>

<style scoped>
h1, p{
  color: #a09d9d;
  position: absolute; /* Forces it to the top */
  top: 60px;
  font-size: 24px;
  width: 100%;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
}
h1 {
  left: 45vw;
  letter-spacing: 3px;
}
p{
  top: 120px;
  left: 150px;
  font-size: 75px;
  font-weight: 200;
  letter-spacing: 6px;
}

.marquee {
  overflow: hidden;
  white-space: nowrap; 
}

.marquee p {
  display: inline-block;
  animation: marquee 30s linear infinite; /* Adjust duration as needed */
}

@keyframes marquee {
  from {
    transform: translateX(100%); /* Start off-screen */
  }
  to {
    transform: translateX(-100%); /* Move completely to the left */
  }
}

@media (max-width: 1024px) {
  h1{
  top: 30px;
 left: 35%;
}
p {
  top: 74px;
  font-size: 56px;
}
}
</style>
