<template>
  <div class="container">
    <h1>Обо мне</h1>
    <p>
      Предоставляю большой спектр современных услуг по реконструкции волос. Регулярно провожу
      обучения, повышаю свою компетентность и ввожу в работу новые улучшенные продукты. Чувствую,
      понимаю и люблю волосы! Умею с ними работать! Веду блог в Instagram.
    </p>
    <div class="images-wrapper">
      <div class="left-col">
        <img id="image-up" :src="image1" alt="Image" />
        <img id="image-down" :src="image2" alt="Image" />
        <p>В салоне также имеется массажёр для ног</p>
      </div>
      <div class="right-col">
        <img id="image-certificate" :src="image3" alt="Image" />
        <p>Сертификат о повышении квалификации по<br />реконструкции волос с правом преподавания</p>
      </div>
    </div>
  </div>
</template>

<style></style>
<script setup lang="ts">
import image1 from '@/assets/images/AboutView/sonya-about1.jpg'
import image2 from '@/assets/images/AboutView/sonya-about2.jpg'
import image3 from '@/assets/images/AboutView/sonya-about3.jpg'
</script>

<style scoped>
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
}

.images-wrapper {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 20px;
}

.images-wrapper img {
  width: 100%;
}

.left-col {
  order: 0;
  display: flex;
  flex-direction: column;
  width: 400px;
}

.left-col p {
  margin-top: 5px;
}

.right-col {
  order: 1;
  width: 400px;
}

#image-down {
  margin-top: 30px;
}

@media (max-width: 768px) {
  .images-wrapper {
    flex-direction: column;
    align-items: center;
  }

  .right-col {
    order: 0;
  }

  .left-col {
    order: 1;
  }
}
</style>
