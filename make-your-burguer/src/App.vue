<script setup>
import '@/assets/main.css'
import { RouterView } from 'vue-router';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <Navbar :logo="logo_src" :alt="app_name" />

  <RouterView />

  <Footer />
</template>

<script>
export default {
  data() {
    return {
      app_name: "Make Your Burguer",
      logo_src: "/img/logo.png"
    }
  }
}
</script>
