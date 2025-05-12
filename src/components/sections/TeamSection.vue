<template>
    <section class="team" id="team">
      <div class="bg-dots"></div>
      <div class="container">
        <h2>Nosso Time</h2>
        <p>Contamos com especialistas experientes e apaixonados por tecnologia, prontos para enfrentar os desafios mais complexos.</p>
        
        <div class="team-grid">
          <div 
            v-for="(member, index) in teamMembers" 
            :key="index" 
            class="team-card"
          >
            <div class="team-avatar">
              <svg viewBox="0 0 24 24">
                <path d="M12 11a4 4 0 1 0 0-8 4 4 0 0 0 0 8z"></path>
                <path d="M6 21v-2a4 4 0 0 1 4-4h4a4 4 0 0 1 4 4v2"></path>
              </svg>
            </div>
            <h3 class="team-name">{{ member.name }}</h3>
            <div class="team-role">{{ member.role }}</div>
            <p class="team-bio">{{ member.bio }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'TeamSection',
    data() {
      return {
        teamMembers: [
          {
            name: 'Marcelo Santos',
            role: 'CEO & Fundador',
            bio: 'Visionário de tecnologia com mais de 15 anos de experiência em transformação digital e estratégia de TI para grandes empresas.'
          },
          {
            name: 'Juliana Costa',
            role: 'CTO',
            bio: 'Especialista em arquitetura de sistemas com foco em soluções cloud-native e infraestrutura escalável para ambientes complexos.'
          },
          {
            name: 'André Oliveira',
            role: 'Head de Cibersegurança',
            bio: 'Profissional certificado em segurança da informação com experiência em proteção de dados e implementação de políticas de governança.'
          },
          {
            name: 'Carolina Lima',
            role: 'Especialista em Cloud',
            bio: 'Expert em migração e otimização de ambientes cloud com foco em AWS, Azure e GCP para empresas de diferentes portes e segmentos.'
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  .team {
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
  
  .team-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 30px;
    margin-top: 40px;
  }
  
  .team-card {
    background: var(--bg-card);
    border-radius: 15px;
    padding: 30px;
    text-align: center;
    transition: all 0.3s ease;
    border: 1px solid rgba(57, 196, 255, 0.1);
  }
  
  .team-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  }
  
  .team-avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: linear-gradient(45deg, var(--accent-blue), var(--accent-purple));
    margin: 0 auto 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    box-shadow: 0 5px 15px rgba(57, 196, 255, 0.3);
  }
  
  .team-avatar svg {
    width: 50px;
    height: 50px;
    fill: white;
  }
  
  .team-name {
    font-size: 1.3rem;
    margin-bottom: 5px;
    background: linear-gradient(to right, var(--accent-blue), var(--accent-cyan));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }
  
  .team-role {
    color: var(--accent-purple);
    font-weight: 600;
    margin-bottom: 15px;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
  
  .team-bio {
    font-size: 0.95rem;
    opacity: 0.8;
  }
  
  @media (max-width: 992px) {
    .team-grid {
      grid-template-columns: 1fr;
    }
  }
  </style>