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
  overflow: hidden; /* Prevents content from overflowing */
  background: url("/src/assets/images/pp.jpeg") no-repeat center;
  background-size: cover;
  color: aliceblue;
  text-align: center;
  position: relative;
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
}

/* Text Content */
.wrapper h1 {
  font-size: 50px;
  margin: 10px 0;
}

.wrapper h2 {
  font-size: 30px;
}

.wrapper h3 {
  font-size: 25px;
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
  gap: 15px;
}

/* Hire Me Button */
.hire-me {
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  padding: 12px 20px;
  background: crimson;
  color: white;
  border-radius: 10px;
  margin-top: 3rem;
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
  position: absolute;
  bottom: 30px;
  right: 50px;
  font-size: 30px;
  animation: blink 5s infinite;
  color: white;
  text-decoration: none;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

/* RESPONSIVENESS */
@media (max-width: 1024px) {
  .wrapper h1 {
    font-size: 40px;
  }

  .wrapper h2 {
    font-size: 28px;
  }

  .wrapper h3 {
    font-size: 22px;
  }
}

@media (max-width: 768px) {
  .intro {
    height: 100vh;
    padding: 20px;
  }

  .wrapper h1 {
    font-size: 36px;
  }

  .wrapper h2 {
    font-size: 26px;
  }

  .wrapper h3 {
    font-size: 20px;
  }

  .hire-me {
    font-size: 16px;
    padding: 10px 16px;
  }

  .arrow {
    font-size: 24px;
  }
}

@media (max-width: 480px) {
  .wrapper h1 {
    font-size: 30px;
  }

  .wrapper h2 {
    font-size: 22px;
  }

  .wrapper h3 {
    font-size: 18px;
  }

  .hire-me {
    font-size: 14px;
    padding: 8px 14px;
  }

  .arrow {
    font-size: 20px;
  }
}
</style>
