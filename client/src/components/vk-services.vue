<template>
    <div class="services" id="nosotros">
      <div class="section-name">
        Quiénes somos
      </div>
      <div class="section-header">
        {{ slogan }}
      </div>
      <div class="section-description">
        {{ text }}
      </div>
      <div class="contents">
        <div class="service" v-for="(service, i) in services" :key="i">
          <div class="service-image">
            <img :src="service.image.src" :alt="service.image.alt" height="100%"/>
          </div>
          <div class="service-details">
            <div class="service-icon">
              <img :src="service.icon.src" :alt="service.icon.alt" height="60%" width="60%"/>
            </div>
            <div class="service-name">
              {{ service.name }}
            </div>
            <div class="service-text">
              {{ service.text }}
            </div>
            <div class="service-text-mobile">
              <button class="seemore" @click="service.show = !service.show" v-if="!service.show">Ver más</button>
              <button class="seemore" @click="service.show = !service.show" v-if="service.show">Ver menos</button><div class="service-text-mobile-inner" v-if="service.show">
                {{ service.text }}
              </div>
            </div>
            <div class="service-actions">
              <br>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'HelloWorld',
    data: () => ({
      services: [
        {
          show: false,
          image: {
            src: require("@/assets/images/services/experiencia.webp"),
            alt: "Imagen de casa con llave",
          },
          icon: {
            src: require("@/assets/icons/llave-de-casa.svg"),
            alt: "Icono de llave de casa",
          },
          name: "Más de 30 años de experiencia",
          text: "Nuestra trayectoria garantiza confianza y profesionalismo. ¡30 años liderando en gestión de comunidades!"
        },
        {
          show: false,
          image: {
            src: require("@/assets/images/services/servicio-integral.webp"),
            alt: "Escritorio con papeles y ordenador",
          },
          icon: {
            src: require("@/assets/icons/soporte-tecnico.svg"),
            alt: "Icono de mano con llave inglesa",
          },
          name: "Servicios integrados",
          text: "Gestión completa: contabilidad, incidencias y más. ¡Todo para la tranquilidad de tu comunidad!"
        },
        {
          show: false,
          image: {
            src: require("@/assets/images/services/atencion-cliente.webp"),
            alt: "Foto de micro de unos cascos",
          },
          icon: {
            src: require("@/assets/icons/conversacion.svg"),
            alt: "Icono de personas conversando",
          },
          name: "Atención personalizada",
          text: "Nos adaptamos a tus necesidades. Nuestro compromiso es brindar un servicio a tu medida."
        },
        {
          show: false,
          image: {
            src: require("@/assets/images/services/profesionalismo.webp"),
            alt: "Manos estrecandose",
          },
          icon: {
            src: require("@/assets/icons/calidad.svg"),
            alt: "Icono sello calidad"
          },
          name: "Transparencia y confianza",
          text: "Equipo dedicado y altamente cualificado. Confía en nosotros para una gestión profesional y eficiente de tu comunidad."
        }
      ],
      slogan: "Dedicados a tu comunidad desde 1994",
      text: "Conoce a GM Fincas: 30 años de experiencia en gestión de comunidades. Tu tranquilidad es nuestra prioridad. Bienvenido.",
    })
  }
  </script>
  
  <style scoped>
    .section-name {
      margin-bottom: 10px;
      font-weight: bold;
      font-family: var(--vk-title-font);
      color: var(--vk-primary);
      font-size: 22px;
      padding-left: 2px;
      padding-right: 2px;
    }
    .section-header {
      font-size: 40px;
      width: 50%;
      font-weight: bold;
      font-family: var(--vk-title-font);
      color: var(--vk-text)
    }
    .section-description {
      font-size: 20px;
      width: 60%;
      margin-top: 30px;
      margin-bottom: 50px;
      font-family: var(--vk-text-font);
      max-width: 800px;
      color: var(--vk-text)
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
    .service {
      width: calc(25% - 50px);
      max-width: 300px;
      overflow: hidden;
      display: flex;
      align-items: center;
      flex-direction: column;
      position: relative;
      color: var(--vk-text-light)
    }
    .service-image {
      width: 100%;
      aspect-ratio: 2/3;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      overflow: hidden;
      border-radius: 10px;
      overflow: hidden;
    }
    .service-image img {
      flex-shrink: 0;
      min-width: 100%;
      min-height: 100%;
      object-fit: cover;
      transition: transform .25s ease-out, filter .25s ease-out;
    }
    .service-image:hover img {
      filter: blur(3px) brightness(.8);
      transform: scale(1.2);
    }
    .service-details {
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      border: 1px solid var(--vk-text-light);
      box-shadow: 0px 0px 2px 0px var(--vk-text);
      border-radius: 10px;
      position: relative;
      background: var(--vk-background);
      width: calc(100% - 30px);
      padding-top: 70px;
      height: fit-content;
      transform: translateY(-33%);
    }
    .service-icon {
      height: 100px;
      width: 100px;
      position: absolute;
      top: -50px;
      box-sizing: border-box;
      border: 4px solid var(--vk-primary);
      border-radius: 50%;
      background: var(--vk-background);
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .service-icon img {
      filter: invert(80%) sepia(23%) saturate(4687%) hue-rotate(341deg) brightness(118%) contrast(96%);
    }
    .service-name {
      font-weight: bold;
      font-family: var(--vk-title-font);
      font-size: 22px;
    }
    .service-text {
      margin-top: 20px;
      font-size: 18px;
      font-family: var(--vk-text-font);
      margin-bottom: 20px;
      width: 85%;
    }
    .seemore {
      border: 2px solid transparent;
      border-radius: 5px;
      width: 150px;
      height: 35px;
      font-size: 16px;
      text-transform: uppercase;
      margin-bottom: 15px;
      color: var(--vk-primary);
      font-weight: bold;
      transition: border .3s ease-out;
      background: none;
      cursor: pointer;
      min-width: fit-content !important;
    }
    .service-text-mobile {
      padding-top: 20px;
      display: none;
      margin-bottom: -10px;
    }
    .service-text-mobile-inner {
      height: fit-content;
      padding: 5px 20px 15px 20px;
    }
    @media (max-width: 600px) {
      .service {
        width: calc(100% - 40px);
        max-width: 1000px;
        margin-bottom: -10px;
      }
      .service-image {
        aspect-ratio: 5/5;
      }
      .service-icon {
        height: 80px;
        width: 80px;
        top: -40px;
      }
      .service-details {
        padding-top: 50px;
        min-height: 80px;
      }
      .service-text {
        display: none;
      }
      .service-text-mobile {
        display: block;
      }
      .contents {
        flex-wrap: wrap;
      }
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
      .service {
        width: calc(100% - 40px);
        max-width: 1000px;
        margin-bottom: -30px;
      }
      .service-image {
        aspect-ratio: 4/2;
      }
      .contents {
        flex-wrap: wrap;
      }
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
      .section-details {
        height: 210px;
      }
    }
    @media (min-width: 801px) and (max-width: 1200px) {
      .service {
        width: calc(50% - 50px);
        max-width: 400px;
        margin-bottom: -30px;
      }
      .service-image {
        aspect-ratio: 2/2;
      }
      .services {
        padding-left: 20px;
        padding-right: 20px;
      }
      .contents {
        flex-wrap: wrap;
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
      .service-details {
        height: 230px;
      }
    }
    @media (min-width: 1200px) {
      .service-details {
        height: 250px;
      }
    }
  </style>
  