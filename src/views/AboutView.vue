<template>
  <div class="container">
    <h1 class="header-about">Обо мне</h1>
    <p class="text-container">
      Приветствую!<br /><br />
      Меня зовут София Данилова — и я мастер и преподаватель по кератину с медицинским
      образованием!<br /><br />
      Именно это делает меня уникальной в мире красоты. Я гарантирую вам безопасность и
      профессионализм на каждом этапе работы.<br /><br />
      У меня более 2-х лет опыта, за это время я постоянно обучалась и развивалась.<br /><br />
      Мое ПЕРВОЕ обучение по кератину прошло в июле 2022 года, затем я получила ВТОРОЕ базовое
      обучение и повышение по холодным методам в апреле 2023.<br /><br />
      Также я прошла ТРЕТЬЕ углубленное обучение по холодным уходам и восстановлению волос и на
      ЧЕТВЕРТОМ обучении изучила пилинги — все это в 2023 году.<br /><br />
      И, наконец, в октябре 2024 года я завершила свое ПЯТОЕ инструкторское обучение с правом
      преподавания!<br /><br />
      Представляете? Пять обучений в копилке моего профессионализма!<br />
      Благодаря этому, мне доверяют многие, и у меня уже есть своя клиентская база.<br />
      Доверьтесь и вы! ♥️<br /><br />
      Я готова восстановить и преобразить ваши волосы, работаю на совесть и стремлюсь к тому, чтобы
      каждый клиент был доволен своим образом.<br /><br />
      С любовью,<br /><br />
      София 🌸
    </p>
    <div class="images-wrapper">
      <div class="left-col">
        <img id="image-up" :src="image1" alt="Image" />
        <img id="image-down" :src="image2" alt="Image" />
        <p>В салоне также имеется массажёр для ног</p>
      </div>
      <div class="right-col">
        <img id="image-certificate" :src="image3" alt="Image" />
        <p>Сертификат о повышении квалификации по реконструкции волос с правом преподавания</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import image1 from '@/assets/media/AboutView/sonya-about1.jpg'
import image2 from '@/assets/media/AboutView/sonya-about2.jpg'
import image3 from '@/assets/media/AboutView/sonya-about3.jpg'
import { onMounted } from 'vue'

onMounted(() => {
  document.title = 'Обо мне'
})
</script>

<style scoped>
.text-container {
  padding: 10px 10px 0;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px 20px;
}

.images-wrapper {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 20px;
  /*padding: 0 20px 20px;*/
}

.images-wrapper img {
  width: 100%;
}

.header-about {
  margin-left: 10px;
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

@media (max-width: 580px) {
  .images-wrapper {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 480px) {
  .right-col {
    width: 100%;
    order: 0;
    /*padding: 0 20px;*/
  }

  .left-col {
    width: 100%;
    order: 1;
    /*padding: 0 20px;*/
  }

  .container {
    padding-bottom: 20px;
  }

  .images-wrapper {
    padding-bottom: 0;
  }
}
</style>
