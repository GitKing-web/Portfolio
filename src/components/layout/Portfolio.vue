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
        <img :src="item.img" alt="" loading="lazy" />
        <h3>{{ item.title }}</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.portfolio {
  background: white;
  color: #333;
  text-align: center;
  padding: 80px 5%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; /* Center everything */
  min-height: 100vh; /* Ensures the section takes the full viewport height */
}

h1 {
  font-size: 42px;
  font-weight: 600;
  margin-bottom: 30px;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: #222;
}

ul {
  display: flex;
  gap: 15px;
  margin-bottom: 35px;
  padding: 0;
  list-style: none;
  flex-wrap: wrap;
  justify-content: center;
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
  background: #ff4c60;
  color: white;
}

.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
  width: 100%;
  max-width: 1200px;
  min-height: 80vh; /* Increased container height */
  align-items: center;
  justify-content: center; /* Ensures items are centered */
}

.item {
  position: relative;
  border-radius: 12px;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background: #f8f9fa;
  box-shadow: 0px 3px 8px rgba(0, 0, 0, 0.1);
  text-align: center; /* Centers text */
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
  h1 {
    font-size: 36px;
  }

  ul {
    flex-wrap: wrap;
    justify-content: center;
  }

  li {
    font-size: 13px;
    padding: 10px 18px;
  }

  .container {
    display: flex;
    flex-direction: column;
    align-items: center; /* Centering items */
    gap: 20px;
    width: 100%;
  }

  .item {
    width: 90%; /* Ensures items don’t shrink too much */
    max-width: 350px;
    /* text-align: center; */
  }

  img {
    width: 100%;
    height: auto;
    border-radius: 12px;
    object-fit: cover;
  }

  h3 {
    position: absolute;
    bottom: 15px;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
    padding: 8px 12px;
    font-size: 14px;
  }
}
</style>
