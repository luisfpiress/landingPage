<template>
    <section class="cases" id="cases">
      <div class="bg-grid"></div>
      <div class="container">
        <h2>Casos de Sucesso</h2>
        <p>Conheça algumas histórias de transformação que impulsionaram os resultados de nossos clientes.</p>
        
        <div class="case-cards">
          <div 
            v-for="(caseStudy, index) in caseStudies" 
            :key="index" 
            class="case-card"
          >
            <div class="case-content">
              <div class="case-company">{{ caseStudy.company }}</div>
              <h3 class="case-title">{{ caseStudy.title }}</h3>
              <p>{{ caseStudy.description }}</p>
              
              <div class="case-metrics">
                <div 
                  v-for="(metric, metricIndex) in caseStudy.metrics" 
                  :key="metricIndex" 
                  class="metric"
                >
                  <div class="metric-value">{{ metric.value }}</div>
                  <div class="metric-label">{{ metric.label }}</div>
                </div>
              </div>
              
              <div class="case-quote">
                <p>"{{ caseStudy.quote }}"</p>
                <div class="quote-author">{{ caseStudy.author }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'CasesSection',
    data() {
      return {
        caseStudies: [
          {
            company: 'FinTech Solutions',
            title: 'Transformação Digital Completa',
            description: 'Implementamos uma estratégia de modernização tecnológica que revolucionou os processos internos e a experiência do cliente.',
            metrics: [
              { value: '68%', label: 'Aumento de eficiência' },
              { value: '45%', label: 'Redução de custos' },
              { value: '3x', label: 'Crescimento de vendas' }
            ],
            quote: 'A parceria com a TechNova transformou completamente nossa abordagem tecnológica e abriu novas possibilidades de crescimento.',
            author: 'Carlos Silva, CTO'
          },
          {
            company: 'LogTech Logistics',
            title: 'Implementação de Segurança Avançada',
            description: 'Desenvolvemos e implementamos uma arquitetura robusta de cibersegurança para proteger dados sensíveis e garantir conformidade regulatória.',
            metrics: [
              { value: '99.9%', label: 'Uptime da plataforma' },
              { value: '100%', label: 'Conformidade regulatória' },
              { value: '0', label: 'Incidentes de segurança' }
            ],
            quote: 'A implementação da TechNova nos permitiu focar no crescimento do negócio sem preocupações com vulnerabilidades de segurança.',
            author: 'Ana Pereira, CEO'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .cases {
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
  
  .case-cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 30px;
    margin-top: 40px;
  }
  
  .case-card {
    background: var(--bg-card);
    border-radius: 15px;
    overflow: hidden;
    transition: all 0.3s ease;
    border: 1px solid rgba(57, 196, 255, 0.1);
    position: relative;
  }
  
  .case-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
  }
  
  .case-content {
    padding: 25px;
  }
  
  .case-company {
    background: linear-gradient(to right, var(--accent-blue), var(--accent-cyan));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    font-size: 1.1rem;
    font-weight: 700;
    margin-bottom: 10px;
  }
  
  .case-title {
    font-size: 1.5rem;
    margin-bottom: 15px;
  }
  
  .case-metrics {
    display: flex;
    gap: 20px;
    margin: 20px 0;
  }
  
  .metric {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .metric-value {
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--accent-orange);
  }
  
  .metric-label {
    font-size: 0.9rem;
    opacity: 0.7;
  }
  
  .case-quote {
    background: rgba(10, 25, 47, 0.5);
    padding: 20px;
    border-radius: 10px;
    font-style: italic;
    position: relative;
    margin-top: 20px;
    border-left: 3px solid var(--accent-blue);
  }
  
  .quote-author {
    margin-top: 10px;
    text-align: right;
    font-size: 0.9rem;
    font-weight: 600;
  }
  
  @media (max-width: 992px) {
    .case-cards {
      grid-template-columns: 1fr;
    }
  }
  </style>