<script setup>
import { ref } from 'vue';

const emit = defineEmits(['toggle-nav']);
const rotateBar = ref(false);

function togglenav() {
  emit('toggle-nav');
  rotateBar.value = !rotateBar.value;
}
</script>

<template>
  <header class="header">
    <div class="wrapper">
      <!-- Left Section -->
      <div class="left">
        <div class="logo"><a href="#intro">KiNG.</a></div>
        <div class="cred">
          <h6>Phone:</h6><span>+234 811 457 8663</span>
          <h6>Email:</h6><span>ekingagada007@gmail.com</span>
        </div>
      </div>

      <!-- Right Section (Mobile Nav Button) -->
      <div class="right">
        <div class="bars" @click="togglenav" :class="{ active: rotateBar }">
          <span class="line1"></span>
          <span class="line2"></span>
          <span class="line3"></span>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
/* HEADER STYLING */
.header {
  width: 100%;
  height: 70px;
  background-color: rgb(2, 2, 41);
  color: aliceblue;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  display: flex;
  align-items: center;
  transition: background 0.3s ease-in-out;
}

/* Wrapper for Flex Layout */
.wrapper {
  width: 100%;
  max-width: 1200px;
  /* margin: 0 auto; */
  padding: 40px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* LEFT SECTION */
.left {
  display: flex;
  align-items: center;
  gap: 30px;
}

/* Logo */
.logo {
  font-size: 40px;
  font-weight: bold;
}

.logo a {
  text-decoration: none;
  color: aliceblue;
  transition: color 0.3s ease-in-out;
}

.logo a:hover {
  color: crimson;
}

/* Contact Information */
.cred {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px;
}

.cred h6 {
  font-size: 12px;
  font-weight: 600;
}

.cred span {
  font-size: 15px;
  font-weight: 500;
  color: lightgray;
}

/* RIGHT SECTION (HAMBURGER MENU) */
.right .bars {
  width: 35px;
  height: 25px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
}

/* Menu Bars */
.bars span {
  width: 100%;
  height: 4px;
  background-color: aliceblue;
  border-radius: 5px;
  transition: all 0.3s ease-in-out;
}

/* Toggle Animation */
.active .line1 {
  transform: translateY(10px) rotate(45deg);
}

.active .line2 {
  opacity: 0;
}

.active .line3 {
  transform: translateY(-10px) rotate(-45deg);
}

/* RESPONSIVENESS */
@media (max-width: 768px) {
  .cred{
    display: none;
  }
  .logo{
    font-size: 20px;
  }
}
</style>
