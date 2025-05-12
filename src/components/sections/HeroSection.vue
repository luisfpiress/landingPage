<template>
    <section class="hero" id="home">
      <div class="bg-grid"></div>
      <div class="container">
        <div class="hero-content">
          <h1>Inovação e Expertise em Tecnologia</h1>
          <p class="hero-subtitle">Transformando ideias em soluções digitais de alto impacto para empresas que desejam liderar o futuro.</p>
          <div class="hero-btns">
            <a href="#contact" class="btn">Agendar Consulta</a>
            <a href="#services" class="btn secondary-btn">Nossos Serviços</a>
          </div>
        </div>
      </div>
      
      <div class="hero-graphic">
        <div class="circuit-graphic">
          <!-- Circuit lines -->
          <div class="circuit-line" v-for="(line, index) in circuitLines" :key="'line-'+index"
               :style="{top: line.top, left: line.left, width: line.width, transform: line.transform}"></div>
          
          <!-- Circuit nodes -->
          <div class="circuit-node" v-for="(node, index) in circuitNodes" :key="'node-'+index"
               :style="{top: node.top, left: node.left}"></div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'HeroSection',
    data() {
      return {
        circuitLines: [
          { top: '30%', left: '10%', width: '40%', transform: 'rotate(45deg)' },
          { top: '60%', left: '20%', width: '60%', transform: 'rotate(-30deg)' },
          { top: '35%', left: '50%', width: '30%', transform: 'rotate(90deg)' },
          { top: '80%', left: '40%', width: '50%', transform: 'rotate(15deg)' }
        ],
        circuitNodes: [
          { top: '20%', left: '15%' },
          { top: '35%', left: '50%' },
          { top: '60%', left: '20%' },
          { top: '70%', left: '60%' },
          { top: '90%', left: '40%' }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    background: var(--bg-primary);
    position: relative;
    padding-top: 80px;
  }
  
  .bg-grid {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
        linear-gradient(rgba(10, 25, 47, 0.3) 1px, transparent 1px),
        linear-gradient(90deg, rgba(10, 25, 47, 0.3) 1px, transparent 1px);
    background-size: 30px 30px;
    z-index: -1;
    opacity: 0.2;
  }
  
  .hero-content {
    width: 50%;
    z-index: 5;
  }
  
  .hero-subtitle {
    font-size: 1.2rem;
    margin-bottom: 30px;
    opacity: 0.8;
  }
  
  .hero-btns {
    display: flex;
    gap: 20px;
    margin-top: 40px;
  }
  
  .secondary-btn {
    background: transparent;
    border: 2px solid var(--accent-blue);
    box-shadow: 0 0 10px rgba(57, 196, 255, 0.3);
  }
  
  .secondary-btn::before {
    background: linear-gradient(45deg, var(--accent-blue), var(--accent-cyan));
  }
  
  .hero-graphic {
    position: absolute;
    top: 50%;
    right: 5%;
    transform: translateY(-50%);
    width: 40%;
    height: 60%;
    z-index: 1;
  }
  
  .circuit-graphic {
    width: 100%;
    height: 100%;
    position: relative;
  }
  
  .circuit-line {
    position: absolute;
    background: var(--accent-blue);
    height: 2px;
    border-radius: 2px;
    box-shadow: 0 0 10px var(--accent-blue);
    animation: glow 3s infinite alternate;
  }
  
  .circuit-node {
    position: absolute;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: var(--accent-purple);
    box-shadow: 0 0 15px var(--accent-purple);
    animation: glow 2s infinite alternate;
  }
  
  @keyframes glow {
    0% {
        opacity: 0.6;
        box-shadow: 0 0 5px currentColor;
    }
    100% {
        opacity: 1;
        box-shadow: 0 0 15px currentColor;
    }
  }
  
  @media (max-width: 992px) {
    .hero-content {
      width: 100%;
      text-align: center;
      padding: 0 20px;
    }
  
    .hero-graphic {
      display: none;
    }
  
    .hero-btns {
      justify-content: center;
    }
  }
  </style>