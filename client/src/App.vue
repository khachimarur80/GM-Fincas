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
      primary: '#fac32a',
      secondary: '#333333',
      accent: '#FFFFFF',
      error: '#FF3333',
      warning: '#FFD700',
      info: '#1E90FF',
      success: '#32CD32',
      text: '#FFFFFF',
      text_secondary: '#CCCCCC',
      text_light: '#F5F5F5',
      text_dark: '#000000',
      background: '#111',
      background_dark: '#111111',
      background_light: '#222222',
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
  background: var(--vk-background);
}
</style>
