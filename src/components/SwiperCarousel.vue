<!-- SwiperCarousel.vue -->
<template>
  <swiper-container
    :slides-per-view="2"
    :space-between="10"
    :loop="true"
    :navigation="true"
    :breakpoints="breakpoints"
    class="swiper-carousel"
    :autoplay="{ delay: 3000, disableOnInteraction: false }"
  >
    <swiper-slide v-for="(item, index) in items" :key="index" lazy="true">
      <a href="#" class="card-link" @click.prevent>
        <img :src="item.thumbnail" class="card-image" :alt="item.alt" loading="lazy" />
        <p class="caption">{{ item.caption }}</p>
      </a>
    </swiper-slide>
  </swiper-container>
</template>

<script setup lang="ts">
import { register } from 'swiper/element/bundle'
import { ref } from 'vue'

register()

defineProps({
  items: {
    type: Array as () => Array<{
      thumbnail: string
      alt: string
      caption: string
    }>,
    required: true,
  },
})

const breakpoints = ref({
  400: {
    slidesPerView: 2,
  },
  768: {
    slidesPerView: 3,
  },
  1024: {
    slidesPerView: 4,
  },
})
</script>

<style scoped>
.swiper-carousel {
  max-width: 1100px;
  margin: 0 auto;
}

.card-link {
  user-select: none;
  display: block;
  background: #fff;
  padding: 18px;
  border-radius: 12px;
  text-decoration: none;
  border: 1px solid transparent;
  box-shadow: 0 10px 10px rgba(0, 0, 0, 0.05);
  transition: 0.2s ease;
  cursor: grab;
}

.card-link:active {
  cursor: grabbing;
}

.card-image {
  width: 100%;
  aspect-ratio: 9 / 16;
  object-fit: cover;
  border-radius: 10px;
}

.caption {
  font-size: 0.95rem;
  font-weight: 500;
  text-align: center;
  margin-top: 10px;
}

swiper-container::part(button-prev),
swiper-container::part(button-next) {
  color: #6c6c6c;
  margin-top: -35px;
  width: 25px;
  height: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
  transition: background 0.1s ease-in-out;
}

swiper-container::part(button-prev) {
  left: -5px;
}

swiper-container::part(button-next) {
  right: -5px;
}

@media (max-width: 768px) {
  swiper-container::part(button-prev),
  swiper-container::part(button-next) {
    display: none;
  }
}
</style>
