<script setup lang="ts">
  import Home from '@/pages/Home/Home.vue';
  import styles from './styles.module.scss'
</script>

<template>
  <div :class="styles.app">
    <div :class="styles.container">
      <Home />
    </div>
  </div>
</template>
