<script setup lang="ts">
// Logic for animations or interactions can be added here
</script>

<template>
  <div class="home">
    <!-- Hero Section -->
    <section id="home" class="hero">
      <div class="hero__background">
        <div class="blob blob--1"></div>
        <div class="blob blob--2"></div>
      </div>
      
      <div class="container hero__container">
        <div class="hero__content">
          <span class="hero__tagline">Detalles que trascienden</span>
          <h1 class="hero__title">
            Creamos <span class="highlight">memorias</span> <br />
            a través del diseño.
          </h1>
          <p class="hero__description">
            Especialistas en imprenta offset, digital y personalización de regalos premium que emocionan.
          </p>
          <div class="hero__actions">
            <a href="https://wa.me/593994389711" target="_blank" class="btn btn--primary">Cotizar Proyecto</a>
            <a href="#services" class="btn btn--outline">Ver Servicios</a>
          </div>
        </div>
        
        <div class="hero__visual">
          <div class="hero__card">
            <div class="hero__card-inner">
              <span class="card-label">Premium Gift Box</span>
              <div class="card-visual">
                <div class="box-outline"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services section-padding">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Nuestros Servicios</h2>
          <p class="section-subtitle">Calidad excepcional en cada impresión y detalle.</p>
        </div>

        <div class="services__grid">
          <div class="service-card">
            <div class="service-card__icon">📦</div>
            <h3 class="service-card__title">Regalos Personalizados</h3>
            <p class="service-card__description">Box premiums con licores, chocolates y papelería fina diseñada a medida.</p>
          </div>
          
          <div class="service-card">
            <div class="service-card__icon">🖨️</div>
            <h3 class="service-card__title">Imprenta Offset & Digital</h3>
            <h4 class="service-card__subtitle">Soluciones Corporativas</h4>
            <p class="service-card__description">Folletos, catálogos, papelería institucional y gran formato con acabados de lujo.</p>
          </div>
          
          <div class="service-card">
            <div class="service-card__icon">✍️</div>
            <h3 class="service-card__title">Social & Eventos</h3>
            <p class="service-card__description">Invitaciones, programas de graduación y detalles para momentos inolvidables.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section id="contact" class="cta section-padding">
      <div class="container">
        <div class="cta__card">
          <div class="cta__content">
            <h2 class="cta__title">¿Tienes una idea en mente?</h2>
            <p class="cta__description">Permítenos ayudarte a hacerla realidad con la mejor calidad del mercado.</p>
            <a href="https://wa.me/593994389711" target="_blank" class="btn btn--gold">Contactar por WhatsApp</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Location Section (Simple) -->
    <section class="location section-padding">
      <div class="container location__container">
        <div class="location__info">
          <h3 class="location__title">Visítanos</h3>
          <p class="location__address">
            Vermont Plaza Norte, Bloque E, Local-38, Guayaquil, Ecuador.
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>

.section-padding {
  padding: 8rem 0;
}

.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  overflow: hidden;
  background: #fbfbfd;
  padding-top: 100px; // Account for fixed header

  @media (min-width: 992px) {
    padding-top: 0; // On desktop, vertical centering usually handles it fine, or we keep it for safety
  }

  &__background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;

    .blob {
      position: absolute;
      filter: blur(80px);
      opacity: 0.4;
      border-radius: 50%;
      
      &--1 {
        top: -10%;
        right: -5%;
        width: 500px;
        height: 500px;
        background: $secondary;
      }
      
      &--2 {
        bottom: 10%;
        left: -10%;
        width: 400px;
        height: 400px;
        background: $accent-pink;
      }
    }
  }

  &__container {
    position: relative;
    z-index: 1;
    display: grid;
    grid-template-columns: 1fr;
    gap: 4rem;
    align-items: center;
    justify-items: center;
    text-align: center;
    max-width: 1300px; // Slightly larger for better PC distribution

    @media (min-width: 992px) {
      grid-template-columns: 1.1fr 0.9fr; // Better balance
      justify-items: start;
      text-align: left;
      margin: 0 auto;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 800px;
    width: 100%;

    @media (min-width: 992px) {
      align-items: flex-start;
      padding-left: 2rem; // Give it some breathing room from the edge
    }
  }

  &__tagline {
    display: inline-block;
    font-family: $font-secondary;
    font-weight: 600;
    font-size: 0.9rem;
    color: $gold;
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 1.5rem;
  }

  &__title {
    font-family: $font-accent;
    font-size: clamp(2.5rem, 8vw, 4.5rem);
    line-height: 1.1;
    color: $primary;
    margin-bottom: 2rem;

    .highlight {
      font-style: italic;
      color: $gold;
    }
  }

  &__description {
    font-family: $font-secondary;
    font-size: clamp(1rem, 2vw, 1.2rem);
    line-height: 1.6;
    color: $text-secondary;
    margin-bottom: 3rem;
    max-width: 600px;
  }

  &__actions {
    display: flex;
    flex-wrap: wrap;
    justify-content: center; // Center buttons
    gap: 1.5rem;

    @media (min-width: 992px) {
      justify-content: flex-start;
    }
  }

  &__visual {
    display: none;
    justify-content: center;

    @media (min-width: 992px) {
      display: flex;
    }
  }

  &__card {
    background: $white;
    width: 320px;
    height: 420px;
    border-radius: 20px;
    padding: 1rem;
    box-shadow: 20px 40px 80px rgba(0, 0, 0, 0.1);
    transform: rotate(5deg);
    transition: transform 0.5s ease;

    &:hover {
      transform: rotate(0deg) translateY(-10px);
    }

    &-inner {
      border: 1px solid rgba($gold, 0.2);
      height: 100%;
      border-radius: 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      position: relative;
    }

    .card-label {
      font-family: $font-accent;
      font-size: 1.5rem;
      margin-top: auto;
    }
    
    .card-visual {
      flex: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;

      .box-outline {
        width: 120px;
        height: 120px;
        border: 2px dashed $gold;
        position: relative;

        &::before {
          content: '';
          position: absolute;
          top: -10px;
          left: 50%;
          transform: translateX(-50%);
          width: 30px;
          height: 15px;
          border: 2px solid $gold;
          border-bottom: none;
        }
      }
    }
  }
}

.section-header {
  text-align: center;
  margin-bottom: 5rem;

  .section-title {
    font-family: $font-accent;
    font-size: 3rem;
    color: $primary;
    margin-bottom: 1rem;
  }

  .section-subtitle {
    font-family: $font-secondary;
    color: $text-secondary;
    font-size: 1.1rem;
  }
}

.services {
  &__grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2.5rem;
  }

  .service-card {
    background: $white;
    padding: 3.5rem 2.5rem;
    border-radius: 24px;
    text-align: center;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    border: 1px solid rgba(0, 0, 0, 0.03);

    &:hover {
      transform: translateY(-15px);
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.1);
      border-color: rgba($gold, 0.3);
    }

    &__icon {
      font-size: 3rem;
      margin-bottom: 2rem;
    }

    &__title {
      font-family: $font-principal;
      font-size: 1.5rem;
      font-weight: 700;
      margin-bottom: 1rem;
      color: $primary;
    }

    &__subtitle {
      font-family: $font-secondary;
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: $gold;
      margin-bottom: 1rem;
    }

    &__description {
      font-family: $font-secondary;
      line-height: 1.6;
      color: $text-secondary;
    }
  }
}

.cta {
  &__card {
    background: $primary;
    border-radius: 40px;
    padding: 6rem 2rem;
    text-align: center;
    color: $white;
    position: relative;
    overflow: hidden;

    &::after {
      content: '';
      position: absolute;
      top: -50%;
      right: -20%;
      width: 400px;
      height: 400px;
      background: rgba($gold, 0.1);
      border-radius: 50%;
      filter: blur(60px);
    }
  }

  &__title {
    font-family: $font-accent;
    font-size: 3.5rem;
    margin-bottom: 1.5rem;
    position: relative;
    z-index: 1;
  }

  &__description {
    font-family: $font-secondary;
    font-size: 1.2rem;
    color: rgba($white, 0.7);
    margin-bottom: 3rem;
    position: relative;
    z-index: 1;
  }
}

.location {
  text-align: center;
  background: #f8f9fa;

  &__title {
    font-family: $font-principal;
    font-size: 1.8rem;
    margin-bottom: 1rem;
  }

  &__address {
    font-family: $font-secondary;
    color: $text-secondary;
    max-width: 500px;
    margin: 0 auto;
    line-height: 1.6;
  }
}

.btn {
  display: inline-block;
  padding: 1.2rem 2.8rem;
  border-radius: 100px;
  font-family: $font-secondary;
  font-weight: 600;
  font-size: 1rem;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;

  &--primary {
    background: $primary;
    color: $white;
    border: 1px solid $primary;

    &:hover {
      background: transparent;
      color: $primary;
      transform: translateY(-2px);
    }
  }

  &--outline {
    background: transparent;
    color: $primary;
    border: 1px solid $primary;

    &:hover {
      background: $primary;
      color: $white;
      transform: translateY(-2px);
    }
  }

  &--gold {
    background: $gold;
    color: $white;
    border: 1px solid $gold;

    &:hover {
      background: transparent;
      color: $gold;
      transform: translateY(-2px);
    }
  }
}
</style>
