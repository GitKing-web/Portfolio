<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const works = ref([
  {
    title: "Banking App",
    img: "/images/banking-app.png",
    description: "A secure and user-friendly banking application with real-time transactions.",
    stack: "Vue.js, TailwindCSS, Firebase",
    link: "#",
  },
  {
    title: "Finance Tracker",
    img: "/images/finance-tracker.png",
    description: "An intuitive finance tracker that helps users manage expenses and savings.",
    stack: "React, Node.js, MongoDB",
    link: "#",
  },
  {
    title: "E-Commerce UI",
    img: "/images/ecommerce-ui.png",
    description: "A modern and responsive e-commerce UI with seamless user experience.",
    stack: "Next.js, Styled-Components",
    link: "#",
  },
  {
    title: "Stock Trading App",
    img: "/images/stock-trading.png",
    description: "An AI-powered stock trading platform with real-time market data.",
    stack: "Vue.js, Python, Flask, WebSockets",
    link: "#",
  },
]);

const currentIndex = ref(0);
let interval = null;

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % works.value.length;
};

const prevSlide = () => {
  currentIndex.value = (currentIndex.value - 1 + works.value.length) % works.value.length;
};

onMounted(() => {
  interval = setInterval(nextSlide, 5000);
});

onUnmounted(() => {
  clearInterval(interval);
});
</script>

<template>
  <div class="works" id="works">
    <h1>My Works</h1>

    <div class="slider">

      <div class="slide">
        <img :src="works[currentIndex].img"  class="work-img" />
        <div class="work-info">
          <h3>{{ works[currentIndex].title }}</h3>
          <p>{{ works[currentIndex].description }}</p>
          <span class="stack">{{ works[currentIndex].stack }}</span>
          <a v-if="works[currentIndex].link" :href="works[currentIndex].link" target="_blank" class="view-project">
            View Project
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Main Section - Center everything */
.works {
  display: flex;
  align-items: center;
  flex-direction: column;
  /* justify-content: center; */
  background: white;
  color: #232a35;
}

h1 {
  text-transform: uppercase;
  font-size: 48px;
  font-weight: bold;
  margin-top: 3rem;
  margin-bottom: 30px;
}

/* Slider Container */
.slider {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  width: 90%;
  max-width: 900px;
  height: 500px; /* Increased height */
}

/* Slide */
.slide {
  background: #f8f9fa;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.15);
  width: 100%;
  height: 100%;
  display: flex;
  overflow: hidden;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

/* Image */
.work-img {
  width: 100%;
  max-width: 650px;
  border-radius: 8px;
}

/* Text Info */
.work-info {
  margin-top: 15px;
  height: 300px;
  overflow: hidden;
  /* text-align: center; */
}

h3 {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

p {
  font-size: 18px;
  color: #555;
  margin-bottom: 8px;
}

.stack {
  display: block;
  font-size: 16px;
  color: #777;
  margin-bottom: 15px;
}

.view-project {
  text-decoration: none;
  color: white;
  background: crimson;
  padding: 10px 20px;
  border-radius: 5px;
  transition: background 0.3s;
}

.view-project:hover {
  background: #d40000;
}

/* Navigation Buttons */
.nav-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.6);
  color: white;
  border: none;
  padding: 12px;
  cursor: pointer;
  font-size: 26px;
  border-radius: 50%;
  transition: 0.3s ease;
}

.nav-button.left {
  left: -50px;
}

.nav-button.right {
  right: -50px;
}

.nav-button:hover {
  background: rgba(0, 0, 0, 0.9);
}

/* Responsive */
@media (max-width: 768px) {
h1{
  font-size: 20px;
  margin-top: 2rem;
}
}
</style>
