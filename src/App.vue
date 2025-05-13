<template>
  <div class="app">
    <!-- Particle lines effect -->
    <div class="particle-line" style="--y: 0.2;"></div>
    <div class="particle-line" style="--y: 0.4;"></div>
    <div class="particle-line" style="--y: 0.6;"></div>
    <div class="particle-line" style="--y: 0.8;"></div>

    <!-- Background glows -->
    <div class="bg-glow bg-glow-1"></div>
    <div class="bg-glow bg-glow-2"></div>

    <the-navbar />
    <hero-section />
    <about-section />
    <services-section />
    <process-section />
    <cases-section />
    <cta-section />
    <the-footer />
  </div>
</template>

<script>
import TheNavbar from './components/layout/TheNavbar.vue'
import TheFooter from './components/layout/TheFooter.vue'
import HeroSection from './components/sections/HeroSection.vue'
import AboutSection from './components/sections/AboutSection.vue'
import ServicesSection from './components/sections/ServicesSection.vue'
import ProcessSection from './components/sections/ProcessSection.vue'
import CasesSection from './components/sections/CasesSection.vue'
import CtaSection from './components/sections/CtaSection.vue'

export default {
  name: 'App',
  components: {
    TheNavbar,
    TheFooter,
    HeroSection,
    AboutSection,
    ServicesSection,
    ProcessSection,
    CasesSection,
    CtaSection
  }
}
</script>

<style>
@import './assets/styles/variables.css';

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', 'Roboto', sans-serif;
}

body {
  background-color: var(--bg-primary);
  color: var(--text-primary);
  line-height: 1.6;
  overflow-x: hidden;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Background Elements */
.bg-glow {
  position: absolute;
  width: 40vw;
  height: 40vw;
  border-radius: 50%;
  filter: blur(100px);
  opacity: 0.07;
  z-index: -2;
}

.bg-glow-1 {
  top: -10%;
  right: -10%;
  background: var(--accent-purple);
}

.bg-glow-2 {
  bottom: -10%;
  left: -10%;
  background: var(--accent-blue);
}

/* Particle Line Effect */
.particle-line {
  position: absolute;
  background: linear-gradient(to right, transparent, var(--accent-blue), transparent);
  height: 1px;
  width: 150px;
  opacity: 0;
  z-index: -1;
  animation: particle-move 8s infinite ease-in-out;
}

@keyframes particle-move {
  0% {
    transform: translateX(-100vw) translateY(calc(100vh * var(--y, 0.5)));
    opacity: 0;
  }
  10% {
    opacity: 0.5;
  }
  90% {
    opacity: 0.5;
  }
  100% {
    transform: translateX(100vw) translateY(calc(100vh * var(--y, 0.5)));
    opacity: 0;
  }
}

/* Utility Classes */
.text-gradient {
  background: linear-gradient(to right, var(--accent-blue), var(--accent-cyan));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.glow {
  filter: drop-shadow(0 0 5px rgba(57, 196, 255, 0.5));
}

/* Global styles for section elements */
section {
  padding: 80px 0;
  position: relative;
  overflow: hidden;
}

h1, h2, h3, h4 {
  font-weight: 700;
  letter-spacing: 0.5px;
  margin-bottom: 20px;
}

h1 {
  font-size: 3rem;
  line-height: 1.2;
  background: linear-gradient(to right, var(--accent-blue), var(--accent-purple));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  text-shadow: 0 0 10px rgba(57, 196, 255, 0.3);
}

h2 {
  font-size: 2.2rem;
  position: relative;
  display: inline-block;
  margin-bottom: 40px;
}

h2::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 60px;
  height: 4px;
  background: linear-gradient(to right, var(--accent-blue), var(--accent-purple));
  border-radius: 2px;
  box-shadow: 0 0 10px rgba(57, 196, 255, 0.5);
}

p {
  margin-bottom: 20px;
  opacity: 0.9;
  font-size: 1.05rem;
}

.btn {
  display: inline-block;
  background: linear-gradient(45deg, var(--accent-purple), var(--accent-blue));
  color: white;
  padding: 12px 30px;
  border-radius: 30px;
  text-decoration: none;
  font-weight: 600;
  letter-spacing: 1px;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(110, 7, 243, 0.4);
  position: relative;
  z-index: 1;
  overflow: hidden;
}

.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 0%;
  height: 100%;
  background: linear-gradient(45deg, var(--accent-cyan), var(--accent-purple));
  transition: all 0.5s ease;
  z-index: -1;
  border-radius: 30px;
}

.btn:hover::before {
  width: 100%;
}

.btn:hover {
  box-shadow: 0 7px 20px rgba(110, 7, 243, 0.6);
  transform: translateY(-2px);
}

/* Responsiveness */
@media (max-width: 992px) {
  h1 {
    font-size: 2.5rem;
  }

  h2 {
    font-size: 2rem;
  }
}
</style>