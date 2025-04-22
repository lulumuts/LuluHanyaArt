<script setup>
import { ref } from 'vue'

const hoverIndex = ref(null)
const items = ref([
  {title: 'Red Rebellion', image: 'RedRebellion.jpeg', description: 'Acrylic on Stretched Canvas, 30" x 40"'},
  {title: 'Glower', image: 'Glower.jpg', description: 'Acrylic on Stretched Canvas, 30" x 40"'},
  {title: 'Beam', image: 'Beam.jpeg', description: 'Acrylic on Stretched Canvas, 18" x 24"'},
  {title: 'Cowrie', image: 'Cowrie.jpeg', description: 'Acrylic on Stretched Canvas, 30" x 40"'},
  {title: 'Goading Glare', image: 'GoadingGlare.jpeg', description: 'Acrylic on Canvas Panel, 30" x 40"'},
  {title: 'Glow', image: 'Glow.png', description: 'Acrylic on Stretched Canvas, 18" x 24"'},
])
const getImagePath = (image) => {
  return new URL(`../assets/images/${image}`, import.meta.url).href
}
</script>



<template>
  <div class="body">
    <div class="content">
      <div class="image-container">
        <Transition  name="blur-fade" mode="out-in">
           <div v-if="hoverIndex !== null" class="image-card">
             <img :src="getImagePath(items[hoverIndex].image)" alt="image" />
             <h1 class="description item-title">{{ items[hoverIndex].title }}</h1>
             <p class="description">{{ items[hoverIndex].description }}</p>
           </div>

           <div v-else class="image-card" >
              <h1>Artist Statement</h1>
              <p><span>The Female Gaze</span>
              is a series of paintings that reimagine the representation of African women—unencumbered, existing fully in our skin.
              In a world where we are all striving to be seen, The Female Gaze normalizes and deconstructs the ‘strong Black woman’ narrative. 
              <br><br>
              While strength remains a truth, this series offers Black women a space to shed their armor and simply be &mdash; beyond society’s gaze.
            </p>
          </div>
          </Transition>
 </div>

    <div class="titles">
      <div class="item card-container"
    v-for="(item, index) in items"
    :key="index"
    @mouseover="hoverIndex = index"
    @mouseleave="hoverIndex = null"
    >
    <p>{{ item.title }}</p>
    
    </div>
    </div>
   
     
     
    </div>
  </div>
</template>

<style scoped>

.titles {
  position: absolute;
  right: 40px;
  font-size: 14.5px;
  color: #b4b1b1;
  top: 380px;
}
.content {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  letter-spacing: 4px;
  font-family: "Montserrat", sans-serif;
  text-transform: uppercase;
  text-align: left;
}
span {
  color: #999999;
  font-weight: 700;
}
.titles .card-container{
  width: 340px;
  margin: 20px;
  text-align: left;
  color: #b4b1b1;
}
.image-container img{
  width: 475px;
  position: absolute;
  left: 0;
  top: -75px;
}
.description {
  position: absolute;
  right: 0;
  left: 500px;
  font-size: 12px;
  letter-spacing: 1px;
  line-height: 18px;
  font-weight: 600;
  text-align: left;
  top: 200px;
}

.item-title{
  top: 180px;
  font-size: 14px;
  color: #555555 !important;
  font-weight: 700;
}
.image-card{
position: absolute;
left: 140px;
top: 400px;
width: 48%;
text-align: justify;
color: #9d9b9b;
line-height: 30px;
}
.image-card h1 {
  padding-bottom: 40px;
  color: #b4b1b1;
  font-family: "Montserrat", sans-serif;
}


.card-container p {
  padding: 16px;
  position: relative;
  display: inline-block;
  letter-spacing: 2px;
  font-family: "Montserrat", sans-serif;
  font-weight: 500;
  text-transform: uppercase;
}
.card-container p:hover {
  cursor: pointer;
}
.card-container p::before {
  content: "\2500\2500\2500\2500\2500\2500\2500\2500\2500";
  padding-right: 20px;
  display: inline-block;
  letter-spacing: 0;
  white-space: nowrap;
  transition: transform 0.25s ease-in-out, opacity 0.25s ease-in-out;
}

.card-container p:hover::before {
  transform: translateX(100px); /* Moves left smoothly */
  cursor: pointer;
}

.blur-fade-enter-active {
  transition: 
    opacity 0.6s cubic-bezier(0.4, 0, 0.2, 1),
    filter 0.7s cubic-bezier(0.4, 0, 0.2, 1);
  will-change: opacity, filter;
}

.blur-fade-leave-active {
  transition: 
    opacity 0.3s ease-out,
    filter 0.3s ease-out;
  will-change: opacity, filter;
}

.blur-fade-enter-from,
.blur-fade-leave-to {
  opacity: 0;
  filter: blur(30px);
}

.blur-fade-enter-to,
.blur-fade-leave-from {
  opacity: 1;
  filter: blur(0);
}

@media (max-width: 1024px) {
  .titles {
  position: relative;
  right: 0;
  text-align: right;
  top: 132px;
  font-size: 14px;
}

.image-card{
position: absolute;
left: 60px;
top: 550px;
width: 75%;
}

.image-card p{
  font-size: 14px;
}
.image-container img{
  width: 360px;
  position: absolute;
  left: 10px;
  top: 16px;
}
.card-container p {
  padding: 8px;
}

}
</style>
