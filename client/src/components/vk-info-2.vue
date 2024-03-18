<template>
  <div class="services" id="donde">
    <div class="section-name">
      Dónde estamos
    </div>
    <div class="section-header">
      {{ slogan }}
    </div>
    <div class="section-description">
      {{ text }}
    </div>
    <div class="contents">
      <iframe
        width="600"
        height="450"
        frameborder="0"
        style="border:0"
        :src="mapUrl"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    slogan: "Nuestra localización",
    text: "Estamos en Calle Castillo, 5, 1º Derecha, 22002 Huesca",
    latitude: 42.139022357828715,
    longitude: -0.40839870270752376,
    zoomLevel: 20,
    apiKey: 'AIzaSyCH6moldAUktxVaVXKz8UY-1cTD3GDZIGU',
  }),
  computed: {
    mapUrl() {
      return `https://www.google.com/maps/embed/v1/view?key=${this.apiKey}&center=${this.latitude},${this.longitude}&zoom=${this.zoomLevel}`;
    }
  },
}
</script>

<style scoped>
  .section-name {
    margin-bottom: 10px;
    font-weight: bold;
    font-family: var(--vk-title-font);
    color: var(--vk-primary);
    font-size: 22px;
  }
  .section-header {
    font-size: 40px;
    width: 50%;
    font-weight: bold;
    font-family: var(--vk-title-font);
  }
  .section-description {
    font-size: 20px;
    width: 60%;
    margin-top: 30px;
    margin-bottom: 50px;
    font-family: var(--vk-text-font);
    max-width: 800px;
  }
  .services {
    width: 100%;
    height: fit-content;
    padding: 50px;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
  .contents {
    width: calc(100%);
    display: flex;
    justify-content: space-evenly;
    max-width: 1400px;
  }
  
  @media (max-width: 600px) {
    .services {
      padding-left: 10px;
      padding-right: 10px;
    }
    .section-description {
      font-size: 16px;
      width: 75%;
    }
    .section-header {
      font-size: 22px;
      width: 90%;
    }
    .section-name {
      font-size: 18px;
    }
  }
  @media (min-width: 601px) and (max-width: 800px) {
    .section-description {
      font-size: 18px;
      width: 75%;
    }
    .section-header {
      font-size: 30px;
      width: 90%;
    }
    .section-name {
      font-size: 22px;
    }
  }
  @media (min-width: 801px) and (max-width: 1200px) {
    .services {
      padding-left: 20px;
      padding-right: 20px;
    }
    .section-description {
      font-size: 20px;
      width: 60%;
    }
    .section-header {
      font-size: 35px;
      width: 70%;
    }
    .section-name {
      font-size: 24px;
    }
  }
</style>
