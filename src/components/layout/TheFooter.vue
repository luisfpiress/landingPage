<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div>
          <a href="#" class="footer-logo">Tech<span>Nova</span></a>
          <p class="footer-about">Consultoria especializada em soluções tecnológicas para empresas que buscam inovação, eficiência e crescimento sustentável.</p>
          <div class="social-links">
            <a v-for="(social, index) in socialLinks" :key="index" href="#" class="social-link">
              <svg viewBox="0 0 24 24" v-html="social.icon"></svg>
            </a>
          </div>
        </div>
        
        <div>
          <h4 class="footer-heading">Links Rápidos</h4>
          <ul class="footer-links">
            <li v-for="(link, index) in quickLinks" :key="index">
              <a :href="link.href">
                <svg viewBox="0 0 24 24" width="18" height="18">
                  <polyline points="9 18 15 12 9 6"></polyline>
                </svg>
                {{ link.label }}
              </a>
            </li>
          </ul>
        </div>
        
        <div>
          <h4 class="footer-heading">Serviços</h4>
          <ul class="footer-links">
            <li v-for="(service, index) in services" :key="index">
              <a href="#">
                <svg viewBox="0 0 24 24" width="18" height="18">
                  <polyline points="9 18 15 12 9 6"></polyline>
                </svg>
                {{ service }}
              </a>
            </li>
          </ul>
        </div>
        
        <div>
          <h4 class="footer-heading">Contato</h4>
          <ul class="footer-contact">
            <li v-for="(contact, index) in contactInfo" :key="index">
              <svg viewBox="0 0 24 24" v-html="contact.icon"></svg>
              <span v-html="contact.info"></span>
            </li>
          </ul>
        </div>
      </div>
      
      <div class="footer-bottom">
        <div class="copyright">&copy; {{ new Date().getFullYear() }} TechNova</div>
        <div class="footer-nav">
          <a v-for="(link, index) in bottomLinks" :key="index" :href="link.href">
            {{ link.label }}
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'TheFooter',
  data() {
    return {
      socialLinks: [
        {
          icon: '<path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>'
        },
        {
          icon: '<rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>'
        },
        {
          icon: '<path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle>'
        }
      ],
      quickLinks: [
        { href: '#about', label: 'Sobre Nós' },
        { href: '#services', label: 'Serviços' },
        { href: '#process', label: 'Processo' },
        { href: '#cases', label: 'Cases' },
        { href: '#contact', label: 'Contato' }
      ],
      services: [
        'Desenvolvimento Web',
        'Desenvolvimento Mobile',
        'Análise de Dados'
      ],
      contactInfo: [
        {
          icon: '<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle>',
          info: 'Av. Tecnologia, 1500<br>São Paulo, SP - Brasil'
        },
        {
          icon: '<path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path>',
          info: '+55 (11) 4321-9876'
        },
        {
          icon: '<path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline>',
          info: 'contato@technova.com.br'
        }
      ],
      bottomLinks: [
        { href: '#', label: 'Termos de Uso' },
        { href: '#', label: 'Política de Privacidade' },
        { href: '#', label: 'Cookies' },
        { href: '#', label: 'FAQ' }
      ]
    }
  }
}
</script>

<style scoped>
.footer {
  background: var(--bg-secondary); 
  padding: 60px 0 30px;
  position: relative;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 40px;
  margin-bottom: 40px;
}

.footer-logo {
  font-size: 1.6rem;
  font-weight: 800;
  margin-bottom: 20px;
  display: block;
  color: var(--text-primary);
  text-decoration: none;
}

.footer-logo span {
  color: var(--accent-blue);
}

.footer-about {
  opacity: 0.8;
  margin-bottom: 25px;
}

.footer-heading {
  font-size: 1.2rem;
  margin-bottom: 25px;
  position: relative;
}

.footer-heading::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 40px;
  height: 3px;
  background: var(--accent-blue);
  border-radius: 2px;
}

.footer-links {
  list-style: none;
}

.footer-links li {
  margin-bottom: 15px;
}

.footer-links a {
  color: var(--text-primary);
  text-decoration: none;
  opacity: 0.8;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 8px;
}

.footer-links a:hover {
  color: var(--accent-blue);
  opacity: 1;
  transform: translateX(5px);
}

.footer-links svg {
  width: 18px;
  height: 18px;
  stroke: var(--accent-blue);
}

.social-links {
  display: flex;
  gap: 15px;
  margin-top: 20px;
}

.social-link {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(57, 196, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: rgba(57, 196, 255, 0.2);
  transform: translateY(-5px);
}

.social-link svg {
  width: 20px;
  height: 20px;
  fill: none;
  stroke: var(--accent-blue);
  transition: all 0.3s ease;
}

.social-link:hover svg {
  filter: drop-shadow(0 0 5px var(--accent-blue));
}

.footer-contact {
  list-style: none;
}

.footer-contact li {
  margin-bottom: 15px;
  display: flex;
  align-items: flex-start;
  gap: 15px;
}

.footer-contact svg {
  width: 20px;
  height: 20px;
  stroke: var(--accent-blue);
  flex-shrink: 0;
  margin-top: 3px;
}

.footer-bottom {
  padding-top: 30px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
}

.copyright {
  opacity: 0.7;
  font-size: 0.9rem;
}

.footer-nav {
  display: flex;
  gap: 20px;
}

.footer-nav a {
  color: var(--text-primary);
  text-decoration: none;
  opacity: 0.7;
  font-size: 0.9rem;
  transition: all 0.3s ease;
}

.footer-nav a:hover {
  color: var(--accent-blue);
  opacity: 1;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
  }

  .footer-bottom {
    flex-direction: column;
    text-align: center;
  }

  .footer-nav {
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>