<template>
    <section class="about" id="about">
      <div class="bg-dots"></div>
      <div class="container">
        <h2>Sobre a TechNova</h2>
        <div class="about-content">
          <div class="about-text">
            <p>A TechNova é uma consultoria de tecnologia especializada em impulsionar a transformação digital de empresas através de soluções inovadoras e estratégicas. Combinamos expertise técnica com visão de negócios para entregar resultados excepcionais.</p>
            <p>Nossa missão é ser parceira na jornada de crescimento das organizações, oferecendo consultoria personalizada e soluções tecnológicas que geram vantagem competitiva real no mercado.</p>
          </div>
          <div class="about-stats">
            <div 
              v-for="(stat, index) in stats" 
              :key="index" 
              class="stat-card"
            >
              <div class="stat-number">{{ stat.number }}</div>
              <div class="stat-title">{{ stat.title }}</div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'AboutSection',
    data() {
      return {
        stats: [
          { number: '150+', title: 'Projetos concluídos' },
          { number: '98%', title: 'Clientes satisfeitos' },
          { number: '35+', title: 'Especialistas' },
          { number: '8', title: 'Anos de experiência' }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .about {
    background: var(--bg-secondary);
    position: relative;
  }
  
  .bg-dots {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: radial-gradient(rgba(57, 196, 255, 0.15) 1px, transparent 1px);
    background-size: 30px 30px;
    z-index: -1;
  }
  
  .about-content {
    display: flex;
    gap: 60px;
    align-items: center;
  }
  
  .about-text {
    flex: 1;
  }
  
  .about-stats {
    flex: 1;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
  
  .stat-card {
    background: var(--bg-card);
    padding: 25px;
    border-radius: 15px;
    position: relative;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 1px solid rgba(57, 196, 255, 0.1);
  }
  
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 4px;
    height: 100%;
    background: linear-gradient(to bottom, var(--accent-blue), var(--accent-purple));
  }
  
  .stat-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
  }
  
  .stat-number {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 10px;
    background: linear-gradient(to right, var(--accent-blue), var(--accent-purple));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }
  
  .stat-title {
    text-transform: uppercase;
    font-size: 0.9rem;
    letter-spacing: 1px;
    opacity: 0.7;
  }
  
  @media (max-width: 992px) {
    .about-content {
      flex-direction: column;
    }
  
    .stat-card {
      padding: 20px;
    }
  }
  
  @media (max-width: 768px) {
    .about-stats {
      grid-template-columns: 1fr;
    }
  }
  </style>