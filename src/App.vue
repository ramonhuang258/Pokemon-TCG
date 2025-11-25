<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import { Carousel3d, Slide } from 'vue3-carousel-3d'
</script> -->

<template>
  <!-- <header>
     <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div> 
  </header>
  
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

  <main class="container">
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
      <swiper-slide><img class="carouselItem" src="./assets/logos/mew_logo.png" /></swiper-slide
      ><swiper-slide><img class="carouselItem" src="./assets/logos/blk_logo.png" /></swiper-slide
      ><swiper-slide><img class="carouselItem" src="./assets/logos/wht_logo.png" /></swiper-slide
      ><swiper-slide><img class="carouselItem" src="./assets/logos/paf_logo.png" /></swiper-slide
      ><swiper-slide><img class="carouselItem" src="./assets/logos/dri_logo.png" /></swiper-slide>
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
  </main>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
// import { Carousel3d, Slide } from 'vue3-carousel-3d'
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import { EffectCoverflow, Pagination, Navigation, Autoplay, Thumbs } from 'swiper/modules'
// import 'swiper/css/effect-coverflow'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import 'swiper/css/autoplay'
import 'swiper/css/thumbs'

export default {
  components: {
    // Carousel3d,
    // Slide,
    Swiper,
    SwiperSlide,
  },
  setup() {
    const thumbsSwiper = ref(null)

    const setThumbsSwiper = (swiper) => {
      thumbsSwiper.value = swiper
    }

    return {
      thumbsSwiper,
      setThumbsSwiper,
      modules: [Navigation, Autoplay, Thumbs],
    }
  },
  data() {
    return {}
  },
  methods: {},
}
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
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
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 50px 0;
  display: flex;
  flex-direction: column;
}

.container h1 {
  color: white;
  text-align: center;

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

<!-- <carousel-3d
      :count="slides.length"
      :controls-prev-html="'&#10092; '"
      :controls-next-html="'&#10093;'"
      :controls-width="50"
      :controls-height="60"
      :clickable="true"
      :autoplay="true"
      :autoplay-timeout="5000"
      :controls-visible="true"
      :disable3d="disable3d"
      :space="slideSpace"
      :perspective="slidePerspective"
      :display="visible"
      :loop="infinite"
      :animation-speed="animationSpeed"
      :dir="direction"
      :border="slideBorder"
      :start-index="startIndex"
      :inverse-scaling="slideScaling"
      :width="400"
      :height="300"
    >
      <slide v-for="(slide, i) in slides" :index="i">
        :style="((height = 300), (height = 400))"
        <img :src="slide.src" height="270px" width="360px" />
      </slide>
    </carousel-3d> 
    
    
    slides: [
        {
          id: 0,
          index: 0,
          name: 'SV 151',
          src: 'src/assets/logos/mew_logo.png',
        },
        {
          id: 1,
          index: 1,
          name: 'Black Bolt',
          src: 'src/assets/logos/blk_logo.png',
        },
        {
          id: 2,
          index: 2,
          name: 'White Flare',
          src: 'src/assets/logos/wht_logo.png',
        },
        {
          id: 3,
          index: 3,
          name: 'Paldean Fates',
          src: 'src/assets/logos/paf_logo.png',
        },
        {
          id: 4,
          index: 4,
          name: 'Destined Rivals',
          src: 'src/assets/logos/dri_logo.png',
        },
      ],
      -->
