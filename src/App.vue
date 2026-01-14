<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { Carousel3d, Slide } from 'vue3-carousel-3d'
</script> -->

<template>
  <header>
    <a href="#default">Pokemon Scarlet and Violet TCG Expansions</a>

    <div class="header-right">
      <a class="active" href="#home">Home</a>
      <a href="login">Log In</a>
    </div>
  </header>
  <!-- <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>

  orignally used coverflow for the carousel but it didn't quite fit the vision as well so changed it
      :effect="'coverflow'"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
      :slidesPerView="'auto'"
      :centeredSlides="true"-->

  <main class="home-page">
    <div class="container">
      <h1>Popular Sets</h1>
      <swiper
        :grabCursor="true"
        :loop="true"
        :navigation="true"
        :pagination="false"
        :autoplay="true"
        :thumbs="{ swiper: thumbsSwiper }"
        :modules="modules"
        class="mySwiper"
      >
        <swiper-slide
          ><img class="carouselItem" src="./assets/banners/mew-banner.png" /></swiper-slide
        ><swiper-slide
          ><img class="carouselItem" src="./assets/banners/blk_banner_large.jpg" /></swiper-slide
        ><swiper-slide
          ><img class="carouselItem" src="./assets/banners/wht_banner_large.jpg" /></swiper-slide
        ><swiper-slide
          ><img class="carouselItem" src="./assets/banners/paf-banner.png" /></swiper-slide
        ><swiper-slide
          ><img class="carouselItem" src="./assets/banners/dri-banner.png"
        /></swiper-slide>
      </swiper>
      <swiper
        @swiper="setThumbsSwiper"
        :loop="true"
        :spaceBetween="10"
        :slidesPerView="5"
        :watchSlidesProgress="true"
        :modules="modules"
        class="mySwiper2"
      >
        <swiper-slide><img class="carouselItem" src="./assets/logos/mew_logo.png" /></swiper-slide
        ><swiper-slide><img class="carouselItem" src="./assets/logos/blk_logo.png" /></swiper-slide
        ><swiper-slide><img class="carouselItem" src="./assets/logos/wht_logo.png" /></swiper-slide
        ><swiper-slide><img class="carouselItem" src="./assets/logos/paf_logo.png" /></swiper-slide
        ><swiper-slide><img class="carouselItem" src="./assets/logos/dri_logo.png" /></swiper-slide>
      </swiper>
      <DisplayBoard :items="expansions">
        <template #default="{ item }">
          <ExpansionItem :item="item" />
        </template>
      </DisplayBoard>
    </div>
  </main>
</template>

<script>
// import { Carousel3d, Slide } from 'vue3-carousel-3d'
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import { Navigation, Autoplay, Thumbs } from 'swiper/modules'
// EffectCoverflow, Pagination, <- these were previously used imports from swipers but i changed the carousel
// import 'swiper/css/effect-coverflow'
// import 'swiper/css/pagination'
import 'swiper/css/navigation'
import 'swiper/css/autoplay'
import 'swiper/css/thumbs'

import DisplayBoard from './components/DisplayBoard.vue'
import ExpansionItem from './components/ExpansionItem.vue'

export default {
  components: {
    // Carousel3d,
    // Slide,
    Swiper,
    SwiperSlide,
    DisplayBoard,
    ExpansionItem,
  },
  setup() {
    const thumbsSwiper = ref(null)

    const setThumbsSwiper = (swiper) => {
      thumbsSwiper.value = swiper
    }

    const expansions = [
      {
        id: 1,
        name: 'Scarlet and Violet',
        code: 'SV1',
        releaseDate: '2023-03-31',
        totalCards: 258,
        imgSrc: '/src/assets/logos/sv1_logo.png',
      },
      {
        id: 2,
        name: 'Paldea Evolved',
        code: 'PAL',
        releaseDate: '2023-06-09',
        totalCards: 279,
        imgSrc: '/src/assets/logos/pal_logo.png',
      },
      {
        id: 3,
        name: 'Obsidian Flames',
        code: 'OBF',
        releaseDate: '2023-08-11',
        totalCards: 230,
        imgSrc: '/src/assets/logos/obf_logo.png',
      },
      {
        id: 4,
        name: 'Scarlet & Violet 151',
        code: 'MEW',
        releaseDate: '2023-09-22',
        totalCards: 207,
        imgSrc: '/src/assets/logos/mew_logo.png',
      },
      {
        id: 5,
        name: 'Paradox Rift',
        code: 'PAR',
        releaseDate: '2023-11-03',
        totalCards: 266,
        imgSrc: '/src/assets/logos/par_logo.png',
      },
      {
        id: 6,
        name: 'Paldean Fates',
        code: 'PAF',
        releaseDate: '2024-01-26',
        totalCards: 245,
        imgSrc: '/src/assets/logos/paf_logo.png',
      },
      {
        id: 7,
        name: 'Temporal Force',
        code: 'TEF',
        releaseDate: '2024-03-22',
        totalCards: 218,
        imgSrc: '/src/assets/logos/tef_logo.png',
      },
      {
        id: 8,
        name: 'Twilight Masquerade',
        code: 'TWM',
        releaseDate: '2024-05-24',
        totalCards: 226,
        imgSrc: '/src/assets/logos/twm_logo.png',
      },
      {
        id: 9,
        name: 'Shrouded Fables',
        code: 'SFA',
        releaseDate: '2024-08-02',
        totalCards: 99,
        imgSrc: '/src/assets/logos/sfa_logo.png',
      },
      {
        id: 10,
        name: 'Stellar Crown',
        code: 'SCR',
        releaseDate: '2024-09-13',
        totalCards: 175,
        imgSrc: '/src/assets/logos/scr_logo.png',
      },
      {
        id: 11,
        name: 'Surging Sparks',
        code: 'SSP',
        releaseDate: '2024-11-08',
        totalCards: 252,
        imgSrc: '/src/assets/logos/ssp_logo.png',
      },
      {
        id: 12,
        name: 'Prismatic Evolutions',
        code: 'PRE',
        releaseDate: '2025-01-17',
        totalCards: 180,
        imgSrc: '/src/assets/logos/pre_logo.png',
      },
      {
        id: 13,
        name: 'Journey Together',
        code: 'JTG',
        releaseDate: '2025-03-28',
        totalCards: 207,
        imgSrc: '/src/assets/logos/jtg_logo.png',
      },
      {
        id: 14,
        name: 'Destined Rivals',
        code: 'DRI',
        releaseDate: '2025-05-30',
        totalCards: 210,
        imgSrc: '/src/assets/logos/dri_logo.png',
      },
      {
        id: 15,
        name: 'Black Bolt',
        code: 'BLK',
        releaseDate: '2025-07-18',
        totalCards: 172,
        imgSrc: '/src/assets/logos/blk_logo.png',
      },
      {
        id: 16,
        name: 'White Flare',
        code: 'WHT',
        releaseDate: '2025-07-18',
        totalCards: 173,
        imgSrc: '/src/assets/logos/wht_logo.png',
      },
    ]

    return {
      thumbsSwiper,
      setThumbsSwiper,
      expansions,
      modules: [Navigation, Autoplay, Thumbs],
    }
  },
}
</script>

<style scoped>
header {
  line-height: 1.5;
  overflow: hidden;
  background-color: teal;
  padding: 15px 10px;
}

header a {
  float: left;
  color: black;
  text-align: center;
  padding: 10px;
  font-family: 'Courier New', Courier, monospace;
  /* font-size: 16px; */
  border-radius: 5px;
}

.header-right a:hover {
  background-color: turquoise;
}

.header-right a.active {
  background-color: rgba(0, 255, 255, 0.712);
  color: white;
}

.header-right {
  float: right;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */

.home-page::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  background-image: url('@/assets/scarlet-violet-background.webp');
  background-size: cover;
  background-position: center;
  opacity: 0.6;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1.5rem 0;
  display: flex;
  flex-direction: column;
}

.container h1 {
  color: white;
  text-align: center;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 500;
  font-size: 2rem;
  background-color: #f34134;
}

.swiper {
  height: 600px;
  width: 100%;

  margin-left: auto;
  margin-right: auto;
}

.mySwiper {
  width: 100%;
  display: block;
}

.mySwiper .swiper-slide img {
  height: 100%;
  width: 100%;
  display: block;
  object-fit: fill;
}

.mySwiper2 {
  height: 20%;
  box-sizing: border-box;
  padding: 10px 0;
  background-color: #ae7bd0;
  display: grid;
  place-items: center;
}

.mySwiper2 .swiper-slide {
  width: 20%;
  height: 100%;
  opacity: 0.4;
}

.mySwiper2 .swiper-slide-thumb-active {
  opacity: 1;
}

.mySwiper2 .swiper-slide img {
  height: 100%;
  width: 100%;
  display: block;
  object-fit: fill;
}
</style>
