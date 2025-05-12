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
          { href: '#team', label: 'Time' }
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
  }
  
  .nav-links li {
    margin-left: 30px;
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
    bottom: 0;
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
    padding: 8px 20px;
  }
  
  @media (max-width: 768px) {
    .navbar-container {
      flex-direction: column;
      gap: 20px;
    }
  
    .nav-links {
      flex-direction: column;
      gap: 15px;
      align-items: center;
    }
  
    .nav-links li {
      margin-left: 0;
    }
  }
  </style>