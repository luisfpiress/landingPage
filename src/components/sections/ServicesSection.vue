<template>
  <section class="services" id="services">
    <div class="bg-grid"></div>
    <div class="container">
      <h2>Nossos Serviços</h2>
      <p>Oferecemos soluções tecnológicas especializadas para impulsionar a inovação e eficiência da sua empresa.</p>
      
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
          title: 'Desenvolvimento Web',
          description: 'Criamos websites e aplicações web responsivas, modernas e de alta performance. Nossas soluções são desenvolvidas com as últimas tecnologias e seguem as melhores práticas de design e SEO.',
          icon: '<path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path>'
        },
        {
          title: 'Desenvolvimento Mobile',
          description: 'Desenvolvemos aplicativos nativos e multiplataforma para iOS e Android que combinam excelente design com funcionalidade intuitiva, criando experiências móveis inovadoras para seus usuários.',
          icon: '<rect x="5" y="2" width="14" height="20" rx="2" ry="2"></rect><line x1="12" y1="18" x2="12" y2="18"></line><path d="M8 2v2M16 2v2"></path>'
        },
        {
          title: 'Análise de Dados',
          description: 'Transformamos dados complexos em insights acionáveis para sua empresa. Utilizamos técnicas avançadas de análise, visualização e inteligência artificial para apoiar a tomada de decisões estratégicas.',
          icon: '<polyline points="22 12 18 12 15 21 9 3 6 12 2 12"></polyline>'
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
  grid-template-columns: repeat(3, 1fr);
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
  width: 70px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 15px;
  margin-bottom: 25px;
  background: rgba(110, 7, 243, 0.1);
  position: relative;
}

.service-icon svg {
  width: 40px;
  height: 40px;
  fill: none;
  stroke: var(--accent-blue);
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  filter: drop-shadow(0 0 5px var(--accent-blue));
}

.service-title {
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: var(--accent-cyan);
}

.service-description {
  margin-bottom: 20px;
  opacity: 0.9;
  flex-grow: 1;
  line-height: 1.7;
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
  margin-top: auto;
}

.service-link:hover {
  gap: 10px;
  color: var(--accent-cyan);
}

@media (max-width: 992px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
}
</style>