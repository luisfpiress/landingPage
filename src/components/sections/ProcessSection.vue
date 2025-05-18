<template>
    <section class="process" id="process">
      <div class="bg-dots"></div>
      <div class="container">
        <h2>Nosso Processo</h2>
        <p>Seguimos uma metodologia estruturada para garantir resultados consistentes e alinhados às necessidades do seu negócio.</p>
        
        <div class="process-steps">
          <div class="process-line"></div>
          <div class="step-cards">
            <div 
              v-for="(step, index) in steps" 
              :key="index" 
              class="step-card"
            >
              <div class="step-number">{{ index + 1 }}</div>
              <h3 class="step-title">{{ step.title }}</h3>
              <p class="step-description">{{ step.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'ProcessSection',
    data() {
      return {
        steps: [
          {
            title: 'Diagnóstico',
            description: 'Analisamos profundamente sua infraestrutura atual, processos e desafios para entender o cenário completo e identificar oportunidades.'
          },
          {
            title: 'Estratégia',
            description: 'Desenvolvemos um plano de ação personalizado com objetivos claros, prioridades e métricas de sucesso alinhados ao seu negócio.'
          },
          {
            title: 'Implementação',
            description: 'Executamos as soluções propostas com metodologias ágeis, garantindo entregas de valor contínuas e adaptação às mudanças.'
          },
          {
            title: 'Otimização',
            description: 'Monitoramos resultados, coletamos feedbacks e realizamos ajustes contínuos para maximizar o retorno sobre o investimento.'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .process {
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
  
  .process-steps {
    margin-top: 50px;
    position: relative;
  }
  
  .process-line {
    position: absolute;
    top: 40px;
    left: 40px;
    width: calc(100% - 80px);
    height: 3px;
    background: linear-gradient(to right, var(--accent-blue), var(--accent-purple));
    z-index: 1;
    border-radius: 3px;
    box-shadow: 0 0 10px rgba(57, 196, 255, 0.5);
  }
  
  .step-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    position: relative;
    z-index: 2;
  }
  
  .step-card {
    background: var(--bg-card);
    border-radius: 15px;
    padding: 30px;
    transition: all 0.3s ease;
    position: relative;
    border: 1px solid rgba(57, 196, 255, 0.1);
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  
  .step-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  }
  
  .step-number {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: linear-gradient(45deg, var(--accent-purple), var(--accent-blue));
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 20px;
    box-shadow: 0 0 15px rgba(57, 196, 255, 0.5);
  }
  
  .step-title {
    font-size: 1.3rem;
    margin-bottom: 15px;
    color: var(--accent-cyan);
  }
  
  .step-description {
    opacity: 0.8;
  }
  
  @media (max-width: 992px) {
    .step-cards {
      grid-template-columns: 1fr;
    }
  }
  
  @media (max-width: 768px) {
    .process-line {
      display: none;
    }
  }
  </style>