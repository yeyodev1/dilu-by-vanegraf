<script setup lang="ts">
import { ref } from 'vue';

const isScrolled = ref(false);

if (typeof window !== 'undefined') {
  window.addEventListener('scroll', () => {
    isScrolled.value = window.scrollY > 50;
  });
}
</script>

<template>
  <header :class="['header', { 'header--scrolled': isScrolled }]">
    <div class="header__container container">
      <div class="header__logo">
        <span class="logo-text">dil<span class="logo-accent">ú</span></span>
        <span class="logo-subtext">by VaneGraf</span>
      </div>
      
      <nav class="header__nav">
        <a href="#home" class="nav-link">Home</a>
        <a href="#services" class="nav-link">Servicios</a>
        <a href="#contact" class="nav-link">Contacto</a>
      </nav>
      
      <div class="header__actions">
        <a href="https://wa.me/593994389711" target="_blank" class="btn btn--primary">WhatsApp</a>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>

.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 1.5rem 0;
  transition: all 0.3s ease;
  background: transparent;

  &--scrolled {
    background: rgba($white, 0.95);
    backdrop-filter: blur(10px);
    padding: 1rem 0;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  }

  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1300px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  &__logo {
    display: flex;
    flex-direction: column;
    line-height: 1;

    .logo-text {
      font-family: $font-principal;
      font-weight: 700;
      font-size: 1.8rem;
      letter-spacing: -1px;
      color: $primary;
      text-transform: lowercase;

      .logo-accent {
        color: $gold;
        position: relative;
        
        &::after {
          content: '';
          position: absolute;
          top: -2px;
          right: -4px;
          width: 6px;
          height: 6px;
          background: $gold;
          border-radius: 50%;
        }
      }
    }

    .logo-subtext {
      font-family: $font-secondary;
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 1px;
      color: $text-secondary;
      margin-top: 2px;
    }
  }

  &__nav {
    display: none;
    gap: 2.5rem;

    @media (min-width: 768px) {
      display: flex;
    }

    .nav-link {
      font-family: $font-secondary;
      font-size: 0.9rem;
      font-weight: 500;
      color: $primary;
      text-decoration: none;
      transition: color 0.3s ease;
      position: relative;

      &::after {
        content: '';
        position: absolute;
        bottom: -4px;
        left: 0;
        width: 0;
        height: 2px;
        background: $gold;
        transition: width 0.3s ease;
      }

      &:hover {
        color: $gold;
        &::after {
          width: 100%;
        }
      }
    }
  }

  .btn {
    padding: 0.6rem 1.2rem;
    border-radius: 50px;
    font-family: $font-secondary;
    font-weight: 600;
    font-size: 0.85rem;
    text-decoration: none;
    transition: all 0.3s ease;

    &--primary {
      background: $primary;
      color: $white;
      border: 1px solid $primary;

      &:hover {
        background: transparent;
        color: $primary;
      }
    }
  }
}
</style>
