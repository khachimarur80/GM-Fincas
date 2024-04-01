<template>
  <div class="navbar">
    <div class="navbar-header">
      <div class="navbar-logo">
        <img :alt="logo.alt" :src="logo.src" height="100%"/>
      </div>
      <div class="navbar-title">
        GM Fincas
      </div>
    </div>
    <div class="navbar-items">
      <a class="navbar-item" v-for="(item, i) in items" :href="item.href" :key="i">
        {{ item.name }}
      </a>
      <a class="navbar-item" href="https://www.tucomunidad.com/#/login" target="_blank">
        Mi cuenta
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    logo: {
      src: require('@/assets/LOGO.webp'),
      alt: 'Logo GM Fincas',
    },
    items: [
      { name: 'Nosotros', href: '/#nosotros'},
      { name: 'Ubicación', href: '/#donde'},
      { name: 'Horarios', href: '/#horarios'},
      { name: 'Contacto', href: '/#contacto'},
    ]
  })
}
</script>

<style scoped>
  .navbar {
    height: 100px;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
    overflow: hidden;
    position: absolute;
    z-index: 1;
    background: rgba(255, 255, 255, .1) !important;
  }
  .navbar-header {
    width: fit-content;
    height: 100% ;
    box-sizing: border-box;
    padding: 10px;
    display: flex;
    gap: 20px;
    z-index: 1;
  }
  .navbar-logo {
    height: 100%;
    box-sizing: border-box;
    padding: 5px;
    aspect-ratio: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .navbar-title {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 10px;
    font-size: 35px;
    transform: scale(.75) translateX(-25%) translateY(25%);
    color: var(--vk-text-dark);
    font-weight: bolder;
    font-family: var(--vk-title-font);
    user-select: none;
  }
  .navbar-items {
    flex: 1;
    justify-content: flex-end; 
    display: flex;
    padding-right: 30px;
    padding-left: 30px;
    gap: 15px;
    box-sizing: border-box;
    min-width: fit-content;
  }
  .navbar-item {
    text-decoration: none;
    min-width: fit-content;
    color: var(--vk-text-dark);
    font-size: 18px;
    padding: 6px 8px 6px 8px;
    position: relative;
    z-index: 2;
    transition: color .3s ease-out;
    font-family: var(--vk-title-font);
    font-weight: bold;
  }
  .navbar-item:before {
    transition: background .15s ease-out;
    content: '';
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    position: absolute;
    background-color: transparent;
    filter: opacity(.5);
    border-radius: 6px;
    z-index: -1;
  }
  .navbar-item:hover:before {
    background: var(--vk-background-light);
  }

  @media (max-width: 492px) {
    .navbar-header {
      height: 80px;
    }
    .navbar {
      height: fit-content;
      padding-bottom: 10px;
      gap: 0px;
    }
    .navbar-item {
      font-size: 3vw;
      transform: scale(1.1);
    }
    .navbar-items {
      padding: 0px;
      justify-content: center;
      gap: 0px;
    }
  }

  @media (min-width: 493px) and (max-width: 900px) {
    .navbar-header {
      height: 80px;
    }
    .navbar {
      height: fit-content;
      padding-bottom: 10px;
      gap: 0px;
    }
    .navbar-items {
      justify-content: center;
    }
  }
</style>
