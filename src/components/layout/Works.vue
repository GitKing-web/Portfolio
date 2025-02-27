<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';

const works = ref([
  {
    title: "Banking App",
    img: "/src/assets/images/banking-app.png",
    description: "A secure and user-friendly banking application with real-time transactions.",
    stack: "Vue.js, TailwindCSS, Firebase",
    link: "#"
  },
  {
    title: "Finance Tracker",
    img: "/src/assets/images/finance-tracker.png",
    description: "An intuitive finance tracker that helps users manage expenses and savings.",
    stack: "React, Node.js, MongoDB",
    link: "#"
  },
  {
    title: "E-Commerce UI",
    img: "/src/assets/images/ecommerce-ui.png",
    description: "A modern and responsive e-commerce UI with seamless user experience.",
    stack: "Next.js, Styled-Components",
    link: "#"
  },
  {
    title: "Stock Trading App",
    img: "/src/assets/images/stock-trading.png",
    description: "An AI-powered stock trading platform with real-time market data.",
    stack: "Vue.js, Python, Flask, WebSockets",
    link: "#"
  }
]);
</script>

<template>
  <div class="works-section" id="works">
    <h1>My Works</h1>
    <swiper
      :modules="[Navigation, Pagination, Autoplay]"
      :slides-per-view="1"
      :space-between="20"
      :navigation="true"
      :pagination="{ clickable: true }"
      :autoplay="{ delay: 3000, disableOnInteraction: false }"
      class="carousel"
    >
      <swiper-slide v-for="(work, index) in works" :key="index" class="slide">
        <div class="work-card">
          <img :src="work.img" :alt="work.title" class="work-img" />
          <div class="work-info">
            <h3>{{ work.title }}</h3>
            <p>{{ work.description }}</p>
            <span class="stack">{{ work.stack }}</span>
            <a v-if="work.link" :href="work.link" target="_blank" class="view-project">View Project</a>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<style scoped>
.works-section {
  background: white;
  color: #232a35;
  text-align: center;
  padding: 80px 5%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  font-size: 48px;
  font-weight: bold;
  margin-bottom: 30px;
}

.carousel {
  width: 100%;
  max-width: 1200px;
}

.slide {
  display: flex;
  justify-content: center;
}

.work-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #f8f9fa;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.work-card:hover {
  transform: scale(1.05);
  box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.15);
}

.work-img {
  width: 100%;
  max-width: 600px;
  border-radius: 8px;
}

.work-info {
  margin-top: 15px;
  text-align: center;
}

h3 {
  font-size: 22px;
  font-weight: bold;
  margin-bottom: 10px;
}

p {
  font-size: 16px;
  color: #555;
  margin-bottom: 8px;
}

.stack {
  display: block;
  font-size: 14px;
  color: #777;
  margin-bottom: 10px;
}

.view-project {
  text-decoration: none;
  color: white;
  background: crimson;
  padding: 8px 16px;
  border-radius: 5px;
  transition: background 0.3s;
}

.view-project:hover {
  background: #d40000;
}

@media (max-width: 768px) {
  h1 {
    font-size: 36px;
  }
}
</style>
