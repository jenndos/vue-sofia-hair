<template>
  <h1 id="label-sofia-danilova">София Данилова</h1>

  <!-- MAIN SECTION -->
  <main>
    <div class="wrapper-image-sonya">
      <img id="image-sonya" src="@/assets/images/HomeView/sonya.png" alt="Sonya Image" />
    </div>
    <div class="services-contacts">
      <!-- Services List -->
      <ul class="services-list">
        <li>• Кератиновое выпрямление</li>
        <li>• Ботокс для волос</li>
        <li>• Нанопластика</li>
        <li>• Многоступенчатое холодное восстановление</li>
        <li>• Уход за натуральными и осветлёнными волосами</li>
        <li>• Индивидуальный подбор составов</li>
      </ul>

      <!-- Contact Information -->
      <div class="contact-info">
        <div class="phone">+7 960 087-20-86</div>
        <div class="address">г. Казань, ул. Кави Наджми 8, офис.&nbsp;23</div>
      </div>

      <!-- Social Media Icons -->
      <div class="media-icons">
        <a href="https://www.instagram.com/sofiya__hair/" target="_blank" aria-label="Instagram">
          <img src="@/assets/icons/instagram_white.png" alt="Instagram" width="37" height="37" />
        </a>
        <a href="https://wa.me/+79600872086" target="_blank" aria-label="WhatsApp">
          <img src="@/assets/icons/whatsapp_icon_white.png" alt="WhatsApp" width="37" height="37" />
        </a>
        <a href="https://t.me/sofia_danilova" target="_blank" aria-label="Telegram">
          <img src="@/assets/icons/telegram_white.png" alt="Telegram" width="37" height="37" />
        </a>
        <a href="https://vk.com/sonyushaaaa" target="_blank" aria-label="VKontakte">
          <img src="@/assets/icons/vk_icon_white.png" alt="VKontakte" width="37" height="37" />
        </a>
      </div>
    </div>
  </main>

  <!-- CLIENT VISIT RESULTS -->
  <div class="experience-info">
    <div class="gray-rectangle">
      <p>5 лет опыта работы</p>
    </div>
    <div class="gray-rectangle">
      <p>более 300 клиентов</p>
    </div>
  </div>

  <h1>Результаты посещения клиентов</h1>

  <SwiperCarousel :items="carouselItems" />

  <ServicesDescription />

  <LocationMap />
</template>

<script setup lang="ts">
import { ref } from 'vue'

import thumbnail1 from '@/assets/images/HomeView/clients/small/client_image_1_small.jpg'
import thumbnail2 from '@/assets/images/HomeView/clients/small/client_image_2_small.jpg'
import thumbnail3 from '@/assets/images/HomeView/clients/small/client_image_3_small.jpg'
import thumbnail4 from '@/assets/images/HomeView/clients/small/client_image_4_small.jpg'
import thumbnail5 from '@/assets/images/HomeView/clients/small/client_image_5_small.jpg'
import thumbnail6 from '@/assets/images/HomeView/clients/small/client_image_6_small.jpg'

import SwiperCarousel from '@/components/SwiperCarousel.vue'
import ServicesDescription from '@/components/ServicesDescription.vue'
import LocationMap from '@/components/LocationMap.vue'

const carouselItems = ref([
  {
    thumbnail: thumbnail1,
    alt: 'Before',
    caption: 'До',
  },
  {
    thumbnail: thumbnail2,
    alt: 'After',
    caption: 'После',
  },
  {
    thumbnail: thumbnail3,
    alt: 'Before',
    caption: 'До',
  },
  {
    thumbnail: thumbnail4,
    alt: 'After',
    caption: 'После',
  },
  {
    thumbnail: thumbnail5,
    alt: 'Before',
    caption: 'До',
  },
  {
    thumbnail: thumbnail6,
    alt: 'After',
    caption: 'После',
  },
])
</script>

<style scoped>
h1 {
  text-align: center;
}

/* =========== MAIN SECTION =========== */

main {
  background-color: #1c1c1c;
  width: 100%;
  height: 500px;
  color: #ffffff;
  display: flex;
  gap: 2rem;
  align-items: center;
  justify-content: center;
  font-size: 22px;
}

/*Sonya Image*/
#image-sonya {
  height: 510px;
}

.wrapper-image-sonya {
  height: 500px;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  color: white;
}

/*Services list*/
ul {
  padding: 0;
  list-style: none;
}

.contact-info {
  margin-top: 13px;
  line-height: 1.3;
}

/*Media icons*/
.media-icons {
  margin-top: 30px;
  display: flex;
  justify-content: space-between;
  width: 200px;
}

.media-icons a {
  width: 37px;
  height: 37px;
  padding: 0;
}

/* =========== CLIENT VISIT RESULTS =========== */

.experience-info {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin: 15px 0;
  font-size: 18px;
}

.experience-info .gray-rectangle {
  background-color: #f2f2f2;
  padding: 5px 14px;
  text-align: center;
}


/* ========================================== */

/* QUERIES */

@media (max-width: 680px) {
  #image-sonya {
    display: none;
  }

  main {
    height: 360px;
    font-size: 20px;
    gap: 0;
  }

  .gray-rectangle .gray-rectangle p {
    font-size: 13px;
  }

  .services-contacts .phone,
  .services-contacts .address {
    font-size: 18px;
  }

  .media-icons {
    display: flex;
    justify-content: space-between;
    margin: 25px auto 0;
  }
}

@media (max-width: 1300px) {
  .wrapper-before-after {
    gap: 10px 0;
  }
}
</style>
