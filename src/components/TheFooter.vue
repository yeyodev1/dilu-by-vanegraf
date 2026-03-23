<script setup lang="ts">
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="footer">
    <div class="footer__container container">
      <div class="footer__grid">
        <!-- Brand Info -->
        <div class="footer__brand">
          <div class="footer__logo">
            <span class="logo-text">dil<span class="logo-accent">ú</span></span>
            <span class="logo-subtext">by VaneGraf</span>
          </div>
          <p class="footer__description">
            Creamos detalles que se convierten en memorias. Imprenta offset, digital y personalización premium.
          </p>
          <div class="footer__social">
            <a href="https://www.instagram.com/dilu.by.vanegraf/" target="_blank" class="social-link">Instagram</a>
          </div>
        </div>

        <!-- Links -->
        <div class="footer__links">
          <h4 class="footer__title">Navegación</h4>
          <ul>
            <li><a href="#home">Inicio</a></li>
            <li><a href="#services">Servicios</a></li>
            <li><a href="#contact">Contacto</a></li>
          </ul>
        </div>

        <!-- Contact Info -->
        <div class="footer__contact">
          <h4 class="footer__title">Contacto</h4>
          <p>Avenida Benjamín Carrión 1-2, Intersección entre Dr. Emilio Romero y Jorge Jara, Vermont Plaza Norte, Bloque E, Local-38, PB, Guayaquil, Ecuador.</p>
          <p><strong>Teléfono:</strong> +593 994389711</p>
          <p><strong>Email:</strong> info@vanegraf.com.ec</p>
        </div>
      </div>

      <div class="footer__legal">
        <div class="footer__legal-data">
          <p><strong>Razón Social:</strong> POZO BELTRAN CARLA VANESSA</p>
          <p><strong>RUC:</strong> 0919842948001</p>
        </div>
        <div class="footer__copyright">
          <p>&copy; {{ currentYear }} Dilú by Vanegraf. Todos los derechos reservados.</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>

.footer {
  background: $primary;
  color: $white;
  padding: 5rem 0 2rem;
  margin-top: auto;

  &__container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1.5rem;
  }

  &__grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 3rem;
    margin-bottom: 4rem;

    @media (min-width: 768px) {
      grid-template-columns: 2fr 1fr 2fr;
    }
  }

  &__logo {
    display: flex;
    flex-direction: column;
    margin-bottom: 1.5rem;

    .logo-text {
      font-family: $font-principal;
      font-weight: 700;
      font-size: 2rem;
      letter-spacing: -1px;
      color: $white;
      text-transform: lowercase;

      .logo-accent {
        color: $gold;
      }
    }

    .logo-subtext {
      font-family: $font-secondary;
      font-size: 0.75rem;
      font-weight: 500;
      letter-spacing: 1px;
      color: rgba($white, 0.6);
    }
  }

  &__description {
    font-family: $font-secondary;
    font-size: 1rem;
    line-height: 1.6;
    color: rgba($white, 0.8);
    margin-bottom: 2rem;
  }

  &__title {
    font-family: $font-principal;
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
    color: $gold;
  }

  &__social {
    .social-link {
      color: $white;
      text-decoration: none;
      font-family: $font-secondary;
      font-weight: 600;
      border-bottom: 1px solid $gold;
      transition: all 0.3s ease;

      &:hover {
        color: $gold;
      }
    }
  }

  &__links {
    ul {
      list-style: none;
      padding: 0;
      
      li {
        margin-bottom: 0.8rem;
        
        a {
          color: rgba($white, 0.8);
          text-decoration: none;
          font-family: $font-secondary;
          transition: color 0.3s ease;

          &:hover {
            color: $gold;
          }
        }
      }
    }
  }

  &__contact {
    p {
      font-family: $font-secondary;
      font-size: 0.95rem;
      line-height: 1.6;
      color: rgba($white, 0.8);
      margin-bottom: 1rem;
    }
  }

  &__legal {
    border-top: 1px solid rgba($white, 0.1);
    padding-top: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    align-items: center;
    text-align: center;

    @media (min-width: 768px) {
      flex-direction: row;
      justify-content: space-between;
      text-align: left;
    }

    &-data {
      p {
        font-family: $font-secondary;
        font-size: 0.8rem;
        color: rgba($white, 0.5);
        margin-bottom: 0.2rem;
      }
    }

    &-copyright {
      p {
        font-family: $font-secondary;
        font-size: 0.8rem;
        color: rgba($white, 0.4);
      }
    }
  }
}
</style>
