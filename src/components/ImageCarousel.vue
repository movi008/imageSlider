<script setup>
import { reactive } from 'vue'
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

const images = reactive([
  {
    id: 1,
    src: 'https://source.unsplash.com/random/300x400?sig=1',
    alt: 'slide-image'
  },
  {
    id: 2,
    src: 'https://source.unsplash.com/random/300x400?sig=2',
    alt: 'slide-image'
  },
  {
    id: 3,
    src: 'https://source.unsplash.com/random/300x400?sig=3',
    alt: 'slide-image'
  },
  {
    id: 4,
    src: 'https://source.unsplash.com/random/300x400?sig=4',
    alt: 'slide-image'
  }
])
</script>


<template>
  <carousel :items-to-show="1.5" :autoplay="1500" :wrap-around="true" :pauseAutoplayOnHover="true">
    <slide v-for="image in images" :key="image.id">
      <div class="carousel__item">
        <img :src="image.src" :alt="image.alt">
      </div>
    </slide>
    <template #addons>
      <navigation />
      <pagination />
    </template>
  </carousel>
</template>

<style></style>