<script setup>
import { ref, computed } from "vue";

const categories = ["Featured", "Web App", "Resume", "Branding"];
const activeCategory = ref("Featured");

const portfolioItems = {
  Featured: [
    { title: "Banking App", img: "/images/photo.png" },
    { title: "Finance Tracker", img: "/images/photo.png" },
    { title: "E-Commerce UI", img: "/images/photo.png" },
    { title: "Stock Trading App", img: "/images/photo.png" },
  ],
  "Web App": [
    { title: "Task Manager", img: "/images/photo.png" },
    { title: "Social Media Dashboard", img: "/images/photo.png" },
    { title: "E-Commerce UI", img: "/images/photo.png" },
    { title: "Stock Trading App", img: "/images/photo.png" },
  ],
  Resume: [
    { title: "Professional Resume", img: "/images/photo.png" },
    { title: "Creative Portfolio", img: "/images/photo.png" },
  ],
  Branding: [
    { title: "Logo Design", img: "/images/photo.png" },
    { title: "Business Card", img: "/images/photo.png" },
  ],
};

const setActiveCategory = (category) => {
  activeCategory.value = category;
};

const filteredItems = computed(() => portfolioItems[activeCategory.value]);
</script>

<template>
  <div class="portfolio" id="portfolio">
    <h1>Portfolio</h1>
    <ul>
      <li
        v-for="category in categories"
        :key="category"
        :class="{ active: activeCategory === category }"
        @click="setActiveCategory(category)"
      >
        {{ category }}
      </li>
    </ul>
    
    <div class="container">
      <div v-for="(item, index) in filteredItems" :key="index" class="item">
        <img :src="item.img" alt="" />
        <h3>{{ item.title }}</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.portfolio {
  background: white;
  color: #333;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  font-size: 42px;
  margin-top: 3rem;
  font-weight: 600;
  margin-bottom: 30px;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: #222;
}

ul {
  display: flex;
  margin: 10px;
  padding: 0;
  list-style: none;
  gap: 20px;
}

li {
  font-size: 14px;
  padding: 12px 24px;
  cursor: pointer;
  border-radius: 25px;
  background: linear-gradient(135deg, #f8f9fa, #e9ecef);
  transition: all 0.3s ease;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #444;
  border: 1px solid #ddd;
}

li.active {
  background: linear-gradient(135deg, #ff4c60, #ff6b81);
  color: white;
  border: none;
  box-shadow: 0px 3px 10px rgba(255, 76, 96, 0.3);
}

li:hover {
  background: #ff6274;
  color: white;
}

.container {
  width: 70%;
  display: flex;align-items: center; justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 3rem;
  overflow: hidden;
  
}

.item {
  width: 220px;
  height: 100%;
  margin-top: 10px 20px;
  display: flex;
  align-items: center; justify-content: center;
  border-radius: 12px;
}

.item:hover {
  transform: scale(1.05);
  box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

img {
  width: 100%;
  height: auto;
  border-radius: 12px;
  object-fit: cover;
  transition: filter 0.3s ease;
}

.item:hover img {
  filter: brightness(90%);
}

h3 {
  position: absolute;
  bottom: 10px;
  left: 10px;
  background: rgba(0, 0, 0, 0.7);
  padding: 6px 12px;
  font-size: 16px;
  font-weight: 500;
  border-radius: 5px;
  color: white;
  transition: opacity 0.3s ease;
}

.item:hover h3 {
  opacity: 0.9;
}

@media (max-width: 768px) {
  h1{
    font-size: 20px;
    margin-top: 2rem;
  }
  ul{
    flex-wrap: wrap;
    justify-content: center;
  }
  li{
    padding: 10px 7px;
    font-size: 13px;
  }
  .item{
    height: 200px;
    width: 100%;
    overflow: hidden;
  }
}

</style>
