<script setup lang="ts">
import MainLayout from '@/layout/MainLayout.vue';
</script>

<template>
  <MainLayout />
</template>

<style lang="scss">
@import "@/styles/index.scss";

body {
  font-family: $font-secondary;
  color: $primary;
  overflow-x: hidden;
}

.container {
  width: 100%;
  max-width: 1300px;
  margin: 0 auto;
  padding: 0 2rem;
}
</style>

