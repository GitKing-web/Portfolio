<script setup>
import { ref } from 'vue';

const sidebar = ref(true);

const closebar = () => {
    sidebar.value = !sidebar.value;
}
</script>

<template>
    <div class="sidebar" v-show="sidebar">
        <div class="nav">
            <ul>
                <li @click="closebar"><a href="#intro">Home</a></li>
                <li @click="closebar"><a href="#portfolio">Portfolio</a></li>
                <li @click="closebar"><a href="#works">Works</a></li>
                <li @click="closebar"><a href="#testimonials">Testimonials</a></li>
                <li @click="closebar"><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.sidebar {
    width: 500px;
    height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 2;
    background-color: rgb(2, 2, 41);
    color: aliceblue;
}

.sidebar .nav {
    display: flex;
    flex-direction: column;
    /* align-items: center; */
    margin: 15rem 5rem;
    justify-content: center;
}

.nav li {
    margin-top: 2rem;
    font-size: 24px;
}
.nav li :hover {
    font-weight: 700;
}

li a {
    text-decoration: none;
    color: aliceblue;
}
</style>