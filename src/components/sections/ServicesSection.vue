<template>
    <section class="services" id="services">
      <div class="bg-grid"></div>
      <div class="container">
        <h2>Nossos Serviços</h2>
        <p>Oferecemos uma gama completa de serviços de consultoria tecnológica para impulsionar a inovação e eficiência da sua empresa.</p>
        
        <div class="services-grid">
          <div 
            v-for="(service, index) in services" 
            :key="index" 
            class="service-card"
          >
            <div class="service-icon">
              <svg viewBox="0 0 24 24" v-html="service.icon"></svg>
            </div>
            <h3 class="service-title">{{ service.title }}</h3>
            <p class="service-description">{{ service.description }}</p>
            <a href="#" class="service-link">Saiba mais <span>&rarr;</span></a>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'ServicesSection',
    data() {
      return {
        services: [
          {
            title: 'Consultoria em TI',
            description: 'Avaliamos sua infraestrutura atual e desenvolvemos estratégias personalizadas para otimizar processos, reduzir custos e aumentar a eficiência operacional.',
            icon: '<path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>'
          },
          {
            title: 'Transformação Digital',
            description: 'Guiamos sua empresa na jornada de modernização tecnológica, implementando soluções digitais inovadoras alinhadas aos seus objetivos estratégicos.',
            icon: '<path d="M12 22c5.523 0 10-4.477 10-10S17.523 2 12 2 2 6.477 2 12s4.477 10 10 10z"></path><path d="M12 16v-4"></path><path d="M12 8h.01"></path>'
          },
          {
            title: 'Cibersegurança',
            description: 'Protegemos seu negócio contra ameaças digitais com soluções avançadas de segurança, análise de vulnerabilidades e implementação de políticas de proteção de dados.',
            icon: '<rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect><path d="M7 11V7a5 5 0 0 1 10 0v4"></path>'
          },
          {
            title: 'Cloud Computing',
            description: 'Desenvolvemos e implementamos estratégias de migração para a nuvem, otimizando recursos, escalabilidade e garantindo maior flexibilidade para sua operação.',
            icon: '<path d="M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z"></path><path d="M12 11v6"></path><path d="M9 14h6"></path>'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .services {
    background: var(--bg-primary);
    position: relative;
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
  
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
    margin-top: 40px;
  }
  
  .service-card {
    background: var(--bg-card);
    border-radius: 15px;
    padding: 30px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
    border: 1px solid rgba(57, 196, 255, 0.1);
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  
  .service-card::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background: linear-gradient(to right, var(--accent-purple), var(--accent-blue));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.5s ease;
  }
  
  .service-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  }
  
  .service-card:hover::after {
    transform: scaleX(1);
  }
  
  .service-icon {
    width: 60px;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 15px;
    margin-bottom: 25px;
    background: rgba(110, 7, 243, 0.1);
    position: relative;
  }
  
  .service-icon svg {
    width: 35px;
    height: 35px;
    fill: none;
    stroke: var(--accent-blue);
    stroke-width: 2;
    stroke-linecap: round;
    stroke-linejoin: round;
    filter: drop-shadow(0 0 5px var(--accent-blue));
  }
  
  .service-title {
    font-size: 1.4rem;
    margin-bottom: 15px;
    color: var(--accent-cyan);
  }
  
  .service-description {
    margin-bottom: 20px;
    opacity: 0.8;
    flex-grow: 1;
  }
  
  .service-link {
    color: var(--accent-blue);
    text-decoration: none;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 5px;
    width: fit-content;
    transition: all 0.3s ease;
  }
  
  .service-link:hover {
    gap: 10px;
    color: var(--accent-cyan);
  }
  
  @media (max-width: 992px) {
    .services-grid {
      grid-template-columns: 1fr;
    }
  }
  </style>