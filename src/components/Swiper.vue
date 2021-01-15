<template>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div :key="image.src" class="swiper-slide" v-for="image in images">
                <a :href="image.src" target="_blank">
                  <img :alt="image.alt" :src="image.src" :title="image.title"/>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
  import * as Swiper from '../assets/js/swiper.min.js';

  export default {
    name: 'Swiper',
    props: {
      images: {
        type: Array,
        required: true
      },
    },
    mounted() {
      new Swiper('.swiper-container', {
        direction: 'horizontal',
        simulateTouch: false,
        speed: 1000,
        loop: true,
        autoplay: {
          delay: 5000
        },
        preloadImages: true,
        updateOnImagesReady: true,
        breakpoints: {
          600: {
            slidesPerView: 1,
            slidesPerColumn: 1,
            slidesPerGroup: 1
          },
          800: {
            slidesPerView: 2,
            slidesPerColumn: 1,
            slidesPerGroup: 1
          },
          1000: {
            slidesPerView: 4,
            slidesPerColumn: 1,
            slidesPerGroup: 1
          },
        }
      });
    }
  }
</script>

<style scoped>
    @import '../assets/css/swiper.min.css';

    .swiper-slide img {
        width: 90% !important;
    }

    @media screen and (max-width: 768px) {
        .swiper-container {
            text-align: center;
            margin-bottom: 30px;
        }
    }
</style>