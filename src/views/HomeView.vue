<script setup>
import { ref } from 'vue'
import Home from '../components/Home.vue'

const activeView = ref('paintings') // 'paintings' or 'statement'

const toggleView = (view) => {
  activeView.value = view
}
</script>

<template>
  <main>
    <div class="header-content">
      <img src="@/assets/images/favicon.png" class="logo"/>
      <h1>Lulu Hanya Art</h1>
    </div>
    <div class="marquee">
      <p>Painter. Designer. Coder</p>
    </div>
    
    <!-- Toggle Buttons -->
    <div class="toggle-container">
      <button 
        @click="toggleView('paintings')" 
        :class="['toggle-btn', { active: activeView === 'paintings' }]"
      >
        Paintings
      </button>
      <button 
        @click="toggleView('statement')" 
        :class="['toggle-btn', { active: activeView === 'statement' }]"
      >
        Statement
      </button>
    </div>

    <!-- Content Views -->
    <div class="content-view">
      <div v-if="activeView === 'paintings'" class="paintings-view">
        <Home />
      </div>
      
      <div v-if="activeView === 'statement'" class="statement-view">
        <div class="artist-statement">
          <h2>Artist Statement</h2>
          <p>
            <span>The Female Gaze</span>
            is a series of paintings that reimagine the representation of African women unencumbered, existing fully in our skin.
            In a world where we are all striving to be seen, The Female Gaze normalizes and deconstructs the 'strong Black woman' narrative. 
            <br><br>
            While strength remains a truth, this series offers Black women a space to shed their armor and simply be beyond society's gaze.
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  overflow-x: hidden !important;
  width: 100%;
  max-width: 100vw;
  margin: 0;
  padding: 0;
}

.header-content {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
}

.logo {
  width: 75px;
  height: 75px;
  margin-bottom: 10px;
  z-index: 2;
}

h1 {
  color: #a09d9d;
  font-size: 20px;
  margin: 0;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  overflow: hidden;
  letter-spacing: 3px;
  z-index: 1;
}

p{
  color: #929292;
  font-size: 75px;
  font-weight: 200;
  letter-spacing: 6px;
  max-width: 80vw;
  margin: 0;
  margin-top: 20px;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  overflow: hidden;
}

.marquee {
  overflow: hidden;
  white-space: nowrap;
  width: 100%;
  max-width: 100vw;
  text-align: center;
  margin-top: 10px;
}

.marquee p {
  display: inline-block;
  animation: marquee 30s linear infinite;
  max-width: 100vw;
}

/* Toggle Buttons */
.toggle-container {
  display: flex;
  justify-content: center;
  gap: 40px;
  margin-top: 40px;
  margin-bottom: 30px;
}

.toggle-btn {
  background: transparent;
  border: none;
  color: #a09d9d;
  padding: 8px 0;
  font-size: 16px;
  font-weight: 500;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  letter-spacing: 2px;
  cursor: pointer;
  transition: all 0.3s ease;
  position: relative;
}

.toggle-btn:hover {
  color: #999999;
}

.toggle-btn.active {
  color: #999999;
  font-weight: 600;
}

.toggle-btn.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #999999;
  transition: all 0.3s ease;
}

/* Content Views */
.content-view {
  width: 100%;
}

.statement-view {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  min-height: 60vh;
  padding: 0 20px;
  margin-top: 60px;
}

.artist-statement {
  max-width: 800px;
  text-align: left;
  color: #9d9b9b;
}

.artist-statement h2 {
  color: #b4b1b1;
  font-size: 28px;
  margin-bottom: 40px;
  letter-spacing: 3px;
  text-transform: uppercase;
  font-family: "Montserrat", sans-serif;
  text-align: left;
}

.artist-statement p {
  font-size: 18px;
  line-height: 1.8;
  color: #9d9b9b;
  margin: 0;
  font-family: "Montserrat", sans-serif;
  text-align: left;
  font-weight: 500;
}

.artist-statement span {
  color: #999999;
  font-weight: 700;
}

@keyframes marquee {
  from {
    transform: translateX(100vw);
  }
  to {
    transform: translateX(-100%);
  }
}

@media (max-width: 1024px) {
  .header-content {
    margin-top: 15px;
  }
  
  .logo {
    width: 60px;
    height: 60px;
  }
  
  h1 {
    font-size: 18px;
  }
  
  p {
    font-size: 56px;
    max-width: 90vw;
    margin-top: 15px;
  }
  
  .marquee {
    margin-top: 5px;
  }
  
  .toggle-container {
    margin-top: 30px;
    margin-bottom: 20px;
  }
  
  .artist-statement h2 {
    font-size: 24px;
    margin-bottom: 30px;
  }
  
  .artist-statement p {
    font-size: 16px;
  }
}
</style>
