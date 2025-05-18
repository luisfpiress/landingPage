<template>
  <section class="cta" id="contact">
    <div class="container">
      <div class="cta-container">
        <div class="cta-bg"></div>
        <div class="cta-content">
          <h2>Impulsione Seu Negócio</h2>
          <p class="cta-subtitle">Entre em contato para uma consulta inicial gratuita e descubra como podemos transformar sua empresa.</p>
          
          <form class="contact-form" @submit.prevent="submitForm">
            <div class="form-group">
              <input 
                type="text" 
                class="form-control" 
                placeholder="Seu nome" 
                required
                v-model="form.name"
              >
            </div>
            <div class="form-group">
              <input 
                type="email" 
                class="form-control" 
                placeholder="Seu e-mail" 
                required
                v-model="form.email"
              >
            </div>
            <div class="form-group">
              <input 
                type="text" 
                class="form-control" 
                placeholder="Empresa"
                v-model="form.company"
              >
            </div>
            <div class="form-group">
              <textarea 
                class="form-control" 
                placeholder="Como podemos ajudar?" 
                required
                v-model="form.message"
              ></textarea>
            </div>
            
            <div class="cta-btn-container">
              <button type="submit" class="btn submit-btn" :disabled="loading">
                {{ loading ? 'Enviando...' : 'Agendar Consulta' }}
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'CtaSection',
  data() {
    return {
      form: {
        name: '',
        email: '',
        company: '',
        message: ''
      },
      loading: false
    }
  },
  methods: {
    submitForm() {
      this.loading = true;
      
      // Simulação de envio de formulário
      setTimeout(() => {
        // Aqui você integraria com uma API real
        console.log('Formulário enviado:', this.form);
        
        // Resetar formulário
        this.form = {
          name: '',
          email: '',
          company: '',
          message: ''
        };
        
        this.loading = false;
        
        // Você pode adicionar uma notificação de sucesso aqui
        alert('Formulário enviado com sucesso! Entraremos em contato em breve.');
      }, 1500);
    }
  }
}
</script>

<style scoped>
.cta {
  background: var(--bg-primary);
  position: relative;
}

.cta-container {
  background: linear-gradient(135deg, rgba(10, 25, 47, 0.9), rgba(26, 26, 46, 0.9));
  border-radius: 20px;
  padding: 60px;
  position: relative;
  overflow: hidden;
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(57, 196, 255, 0.1);
  z-index: 5;
}

.cta-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  opacity: 0.1;
  background-image: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 10px,
      rgba(57, 196, 255, 0.1) 10px,
      rgba(57, 196, 255, 0.1) 20px
  );
}

.cta-content {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.cta h2 {
  margin-bottom: 20px;
}

.cta h2::after {
  left: 50%;
  transform: translateX(-50%);
}

.cta-subtitle {
  font-size: 1.2rem;
  margin-bottom: 40px;
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 20px;
}

.form-control {
  width: 100%;
  padding: 15px 20px;
  border-radius: 8px;
  background: rgba(5, 9, 20, 0.7);
  border: 1px solid rgba(57, 196, 255, 0.2);
  color: var(--text-primary);
  font-size: 1rem;
  transition: all 0.3s ease;
}

.form-control:focus {
  outline: none;
  border-color: var(--accent-blue);
  box-shadow: 0 0 0 2px rgba(57, 196, 255, 0.2);
}

.form-control::placeholder {
  color: rgba(255, 255, 255, 0.5);
}

textarea.form-control {
  min-height: 120px;
  resize: vertical;
}

.cta-btn-container {
  margin-top: 30px;
  display: flex;
  justify-content: center;
}

.submit-btn {
  padding: 12px 40px;
  font-size: 1.05rem;
  border-radius: 30px;
  background: linear-gradient(45deg, var(--accent-purple), var(--accent-blue));
  color: white;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(110, 7, 243, 0.4);
  position: relative;
  overflow: hidden;
  z-index: 1;
}

.submit-btn::before {
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

.submit-btn:hover::before {
  width: 100%;
}

.submit-btn:hover {
  box-shadow: 0 7px 20px rgba(110, 7, 243, 0.6);
  transform: translateY(-2px);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

@media (max-width: 992px) {
  .cta-container {
    padding: 40px 20px;
  }
}
</style>