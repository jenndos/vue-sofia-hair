<template>
  <div class="container">
    <h2 class="title">Как добраться?</h2>
    <p class="address">Ул. Кави Наджми, дом. 8, офис. 2, второй этаж</p>
    <a :href="mapLink" target="_blank" rel="noopener noreferrer">
      <img :src="mapImageSrc" alt="Yandex Map Location" class="map-image" />
    </a>
  </div>
</template>

<script setup lang="ts">
const mapLink =
  'https://yandex.ru/maps/?um=constructor%3Ab2b03670ba62cbf7ae78e06704f67481c625f59cdd737c507b4574f7e7973495&source=constructorStatic'
const mapImageSrc =
  'https://api-maps.yandex.ru/services/constructor/1.0/static/?um=constructor%3Ab2b03670ba62cbf7ae78e06704f67481c625f59cdd737c507b4574f7e7973495&width=600&height=300&lang=ru_RU'
</script>

<style scoped>
.container {
  margin: 0 auto;
  padding: 0 10px;
  max-width: 1100px;
}

.container p {
  font-size: 15px;
}

.map-image {
  width: 100%;
  height: auto;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin: 10px 0;
}

.title {
  margin-bottom: 0.5rem;
}
</style>
