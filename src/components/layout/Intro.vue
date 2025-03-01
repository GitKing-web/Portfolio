<script setup>
import { init } from "ityped";
import { onMounted, ref } from "vue";

const typed = ref(null);

onMounted(() => {
  if (typed.value) {
    init(typed.value, {
      strings: [
        "FullStack Developer",
        "Content Writer",
        "Backend Developer",
        "Cybersecurity Enthusiast",
      ],
      typeSpeed: 100,
      backSpeed: 50,
      backDelay: 1000,
      loop: true,
      showCursor: true,
      cursorChar: "|",
    });
  }
});
</script>

<template>
  <div class="intro" id="intro">
    <div class="content-wrapper">
      <div class="wrapper">
        <h2>Hi There! I'm</h2>
        <h1>King Agada</h1>
        <h3>Freelance <span ref="typed"></span></h3>
      </div>

      <div class="cta-buttons">
        <a href="#contact" class="hire-me">
          <h3>Hire Me</h3>
          <i class="fas fa-briefcase"></i>
        </a>
        <a href="#portfolio" class="arrow">
          <i class="fas fa-arrow-down"></i>
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* General Styling */
.intro {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100%;
  text-align: center;
  position: relative;
  padding: 20px;
  box-sizing: border-box;
  background: url("/images/pp.jpeg") no-repeat center center;
  background-size: cover;
  background-attachment: fixed;
  color: aliceblue;
}

/* Wrapper for content */
.content-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 90%;
  max-width: 800px;
  padding: 20px;
  text-align: center;
}

/* Text Content */
.wrapper h1, .wrapper h2, .wrapper h3 {
  margin: 0;
  padding: 5px 0;
  word-wrap: break-word;
}

.wrapper h1 {
  font-size: 50px;
}

.wrapper h2 {
  font-size: 30px;
}

.wrapper h3 {
  font-size: 25px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 5px;
}

.wrapper span {
  font-weight: bold;
  color: crimson;
}

/* CTA Buttons */
.cta-buttons {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  text-align: center;
}

.hire-me {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: fit-content;
  text-decoration: none;
  padding: 12px 20px;
  background: crimson;
  color: white;
  border-radius: 10px;
  font-size: 18px;
  transition: 0.3s ease-in-out;
}

.hire-me i {
  margin-left: 8px;
  font-size: 20px;
}

.hire-me:hover {
  background: darkred;
}

/* Blinking Arrow */
.arrow {
  font-size: 30px;
  animation: blink 5s infinite;
  color: white;
  text-decoration: none;
  position: static;
  margin-top: 20px;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

/* RESPONSIVENESS */
@media (max-width:768px) {
  .content-wrapper {
    margin-top: -35rem;
  }
  .wrapper h2{
    font-size: 18px;
  }
  .wrapper h3 {
    font-size: 16px;
  }
  .wrapper h1 {
    font-size: 40px;
  }
  .arrow {
    margin-top: 8rem;
  }
  .hire-me{
    margin-top: 2rem;
  }
}
</style>
