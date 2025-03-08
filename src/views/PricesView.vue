<script setup lang="ts">
import TablePrices from '@/components/TablePrices.vue'
import { onMounted } from 'vue'

onMounted(() => {
  document.title = 'Цены'
})
</script>

<template>
  <div class="container">
    <h1>Цены</h1>
    <TablePrices class="table" />
    <div class="additional-info">
      <h1>Допополнительные услуги</h1>
      <h2>Одноступенчатое холодное восстановление / перед горячей процедурой, в день процедуры</h2>
      <p>
        Укрепляет волос изнутри, питает и увлажняет. Продлевает срок действия эффекта кератина /
        ботокса.<br />Стоимость 1000-3000 ₽<br />Длительность 30-40 минут
      </p>
      <h2>Пилинг кожи головы / в день основной процедуры</h2>
      <p>
        Очищает кожу головы от накопившегося сала, ороговевших клеток, стимулирует рост волос.<br />Стоимость
        1500 ₽.<br />Длительность 30 минут
      </p>
      <h2>Диагностика кожи головы трихоскопом, пилинг + увлажнение волос / отдельная процедура</h2>
      <p>Стоимость 2500Р<br />Длительность 1,5-2 часа<br />Подравнивание кончиков - в подарок!</p>
    </div>
  </div>
</template>

<style>
.container {
  margin: 0 auto;
  max-width: 1100px;
  padding: 0 20px 20px;
}

.table {
  margin: 15px auto 0;
}

.additional-info h1 {
  margin-top: 15px;
}

.additional-info h2 {
  margin-top: 15px;
}

.additional-info p {
  margin-top: 5px;
}

#title-promo {
  margin: 15px 0 30px;
}

@media (max-width: 768px) {
  .additional-info h1 {
    line-height: 1.2;
  }

  .additional-info h2 {
    line-height: 1.3;
  }
}
</style>
