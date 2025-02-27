<script setup>
import Header from './components/header/Header.vue';
import Intro from './components/layout/Intro.vue';
import Portfolio from './components/layout/Portfolio.vue'
import Works from './components/layout/Works.vue'
import Contact from './components/layout/Contact.vue';
import Sidebar from './components/Sidebar.vue';
import { ref } from 'vue';
import Testimonials from './components/layout/Testimonials.vue';

const showSidebar = ref(false);
const toggleNav = () => {
  showSidebar.value = !showSidebar.value
}
</script>

<template>
  <div class="home">
    <Header @toggle-nav="toggleNav" />
    <Sidebar v-if="showSidebar" />
    <div class="sections">
      <Intro />
      <Portfolio />
      <Works />
      <Testimonials />
      <Contact />
    </div>
  </div>
</template>

<style scoped>
.home{
  height: 100vh;
}
.sections{
  width: 100%;
  height: calc(100vh - 70px);
  /* background-color: chocolate; */
  position: relative;
  top: 70px;
  scroll-behavior: smooth;
  scroll-snap-type: y mandatory;
  scrollbar-width: none;
  &::-webkit-scrollbar{
    display: none;
  }
}
.sections *{
  width: 100vw;
  height: calc(100vh - 70px);
  scroll-snap-align: start;
}
</style>
