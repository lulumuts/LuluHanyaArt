<script setup>
import { ref } from 'vue'

const items = ref([
  {title: 'Untitled', image: 'painting-untitled.png', description: 'Acrylic on Canvas\nIn Progress', available: false, status: 'in-progress'},
  {title: 'Red Rebellion', image: 'RedRebellion.jpeg', description: 'Acrylic on Stretched Canvas\n30" x 40"', available: true, status: 'available'},
  {title: 'Glow', image: 'Glow.png', description: 'Acrylic on Canvas Panel\n30" x 40"', available: true, status: 'available'},
  {title: 'Glower', image: 'Glower.jpg', description: 'Acrylic on Stretched Canvas\n30" x 40"', available: false, status: 'none'},
  {title: 'Beam', image: 'Beam.jpeg', description: 'Acrylic on Stretched Canvas\n18" x 24"', available: false, status: 'none'},
  {title: 'Cowrie', image: 'Cowrie.jpeg', description: 'Acrylic on Stretched Canvas\n30" x 40"', available: false, status: 'none'},
  {title: 'Audacity', image: 'Audacity.jpeg', description: 'Acrylic on Stretched Canvas\n30" x 40"', available: false, status: 'none'},
  {title: 'Daybreak', image: 'Daybreak.jpeg', description: 'Acrylic on Stretched Canvas\n18" x 24"', available: false, status: 'none'},
])

const getImagePath = (image) => {
  return new URL(`../assets/images/${image}`, import.meta.url).href
}
</script>

<template>
  <div class="gallery-container">
    <div class="image-gallery">
      <div 
        v-for="(item, index) in items" 
        :key="index" 
        class="image-item"
      >
        <div class="image-wrapper">
          <img :src="getImagePath(item.image)" :alt="item.title" />
          <div v-if="item.status === 'available'" class="available-tag">Available</div>
          <div v-if="item.status === 'in-progress'" class="in-progress-tag">In Progress</div>
          <div class="image-overlay">
            <h3 class="image-title">{{ item.title }}</h3>
            <p class="image-description">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.gallery-container {
  width: 100%;
  min-height: 120vh;
  padding: 20px;
  margin: 0;
  margin-top: 50px;
  box-sizing: border-box;
  overflow-x: hidden;
}

.image-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  width: 100%;
  justify-content: flex-start;
}

.image-item {
  flex: 0 0 calc(33.333% - 14px);
  min-width: 300px;
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.image-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
}

.image-wrapper {
  position: relative;
  width: 100%;
  height: 500px;
  overflow: hidden;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.image-item:hover .image-wrapper img {
  transform: scale(1.05);
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.9);
  color: white;
  padding: 40px 20px 20px;
  opacity: 0;
  transition: opacity 0.3s ease;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.image-item:hover .image-overlay {
  opacity: 1;
}

.image-title {
  margin: 0;
  margin-bottom: 15px;
  font-size: 22px;
  font-weight: 600;
  letter-spacing: 2px;
  text-transform: uppercase;
  text-align: center;
  font-family: "Montserrat", sans-serif;
  word-wrap: break-word;
  overflow-wrap: break-word;
}

.image-description {
  margin: 0;
  font-size: 14px;
  font-weight: 400;
  letter-spacing: 1px;
  line-height: 1.6;
  text-align: center;
  font-family: "Montserrat", sans-serif;
  opacity: 0.9;
  max-width: 80%;
  white-space: pre-line;
}

.available-tag {
  position: absolute;
  top: 15px;
  right: 15px;
  background: #4CAF50;
  color: white;
  padding: 8px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: 600;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  letter-spacing: 1px;
  z-index: 3;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

.in-progress-tag {
  position: absolute;
  top: 15px;
  right: 15px;
  background: #FFC107;
  color: #333;
  padding: 8px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: 600;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  letter-spacing: 1px;
  z-index: 3;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

/* Responsive Design */
@media (max-width: 1200px) {
  .image-item {
    flex: 0 0 calc(50% - 10px);
  }
}

@media (max-width: 768px) {
  .gallery-container {
    padding: 15px;
  }
  
  .image-gallery {
    gap: 15px;
  }
  
  .image-item {
    flex: 0 0 100%;
    min-width: unset;
  }
  
  .image-wrapper {
    height: 450px;
  }
}

@media (max-width: 480px) {
  .gallery-container {
    padding: 10px;
  }
  
  .image-gallery {
    gap: 10px;
  }
  
  .image-wrapper {
    height: 400px;
  }
}
</style>
