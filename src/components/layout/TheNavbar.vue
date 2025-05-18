<template>
  <nav class="navbar">
    <div class="container navbar-container">
      <a href="#" class="logo">Tech<span>Nova</span></a>
      <ul class="nav-links">
        <li v-for="item in navItems" :key="item.href">
          <a :href="item.href">{{ item.label }}</a>
        </li>
        <li>
          <a href="#contact" class="btn nav-btn">Contato</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'TheNavbar',
  data() {
    return {
      navItems: [
        { href: '#about', label: 'Sobre' },
        { href: '#services', label: 'Serviços' },
        { href: '#process', label: 'Processo' },
        { href: '#cases', label: 'Cases' },
      ]
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      // Você pode adicionar efeitos de scroll aqui, como:
      // - Mudar cor do navbar ao scrollar
      // - Adicionar classes para destacar o item ativo no menu
    }
  }
}
</script>

<style scoped>
.navbar {
  padding: 20px 0;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  transition: all 0.3s ease;
  background: rgba(5, 9, 20, 0.8);
  backdrop-filter: blur(10px);
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.8rem;
  font-weight: 800;
  color: var(--text-primary);
  text-decoration: none;
  display: flex;
  align-items: center;
}

.logo span {
  color: var(--accent-blue);
}

.nav-links {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  align-items: center; /* Isso alinha verticalmente todos os itens */
}

.nav-links li {
  margin-left: 30px;
  display: flex; /* Isso ajuda a alinhar cada item individualmente */
  align-items: center;
}

.nav-links a {
  color: var(--text-primary);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
  padding: 5px 0;
}

.nav-links a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -5px; /* Ajustado para ficar mais abaixo e alinhar visualmente */
  left: 0;
  background: linear-gradient(to right, var(--accent-blue), var(--accent-purple));
  transition: width 0.3s ease;
}

.nav-links a:hover {
  color: var(--accent-blue);
}

.nav-links a:hover::after {
  width: 100%;
}

.nav-btn {
  padding: 8px 24px !important;
  border-radius: 30px;
  background: linear-gradient(45deg, var(--accent-purple), var(--accent-blue));
  color: white !important;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-decoration: none;
  position: relative;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(110, 7, 243, 0.4);
  z-index: 1;
  display: inline-block; /* Garante comportamento de bloco em linha */
  line-height: normal; /* Normaliza a altura da linha */
}

.nav-btn::after {
  display: none; /* Remover a linha de sublinhado no hover */
}

.nav-btn::before {
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

.nav-btn:hover::before {
  width: 100%;
}

.nav-btn:hover {
  box-shadow: 0 7px 20px rgba(110, 7, 243, 0.6);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .navbar-container {
    flex-direction: column;
    gap: 20px;
  }

  .nav-links {
    flex-direction: column;
    gap: 15px;
  }

  .nav-links li {
    margin-left: 0;
  }
  
  .nav-btn {
    padding: 10px 30px !important;
    margin-top: 5px;
  }
}
</style>