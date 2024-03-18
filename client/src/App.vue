<template>
  <vk-navbar/>
  <vkHero/>
  <vkServices/>
  <vkHorario/>
  <vkDonde/>
  <vkContacto/>
  <vkFooter/>
</template>

<script>
import vkNavbar from './components/vk-navbar.vue'
import vkHero from './components/vk-hero.vue'
import vkServices from './components/vk-services.vue'
import vkHorario from './components/vk-info-1.vue'
import vkDonde from './components/vk-info-2.vue'
import vkContacto from './components/vk-contact-3.vue'
import vkFooter from './components/vk-footer-1.vue'

export default {
  name: 'App',
  components: {
    vkNavbar,
    vkHero,
    vkServices,
    vkHorario,
    vkDonde,
    vkContacto,
    vkFooter
  },
  data: () => ({
    theme: {
      primary: '#2196F3',
      secondary: '#1976D2',
      accent: '#FFC107',
      error: '#f44336',
      warning: '#FF9800',
      info: '#03A9F4',
      success: '#4CAF50',
      text: '#333',
      text_secondary: '#666',
      text_light: '#eee',
      text_dark: '#111',
      background: '#f9f9f9',
      background_dark: '#888',
      background_light: '#ffffff',
      text_font: 'Segoe UI Thin',
      title_font: 'Segoe UI',
    }
  }),
  mounted() {
    for (let key in this.theme) {
      document.documentElement.style.setProperty('--vk-'+key.replace('_', '-'), this.theme[key])
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
html, body {
  margin: 0px;
  padding: 0px;
  scroll-behavior: smooth;
  user-select: none;
}
</style>
