<template>
  <div class="services">
    <div v-for="(service, index) in services" :key="index" class="service-item">
      <h2 class="service-header">
        {{ service.title }}
      </h2>
      <p class="description">
        {{ service.description }}
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
type ServiceKey = 'pealing' | 'keratin' | 'botox' | 'coldRecovery' | 'nanoplastics'

interface Service {
  key: ServiceKey
  title: string
  description: string
}

const services: Service[] = [
  {
    key: 'keratin',
    title: 'Кератиновое выпрямление',
    description:
      'Помогает выпрямить волосы от легких волн до тугих завитков сроком от 3 до 6 месяцев.',
  },
  {
    key: 'botox',
    title: 'Ботокс для волос',
    description:
      'Помогает избавится от легкого пушка, разглаживает волосы, возможен легкий выпрямляющий эффект. Срок носки до 3х месяцев.',
  },
  {
    key: 'nanoplastics',
    title: 'Нанопластика',
    description:
      'Помогает выпрямить самые тугие кудри. Выполняется исключительно на волосах хорошего качества! Не подходит для осветленных волос! Срок носки до 8 месяцев.',
  },
  {
    key: 'coldRecovery',
    title: 'Холодное восстановление',
    description:
      'Многоступенчатое холодное восстановление - максимально бережная процедура. Помогает восстановить волосы на молекулярном уровне, восстанавливает водный баланс и липидный слой. Обеспечивает внутриклеточную реконструкцию. После волосы блестящие, мягкие, плотные. Подходит беременным, кормящим и детям. Для сильно поврежденных волос требуется курс.',
  },
]
</script>

<style scoped>
/* Existing styles remain unchanged */
.services {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 10px;
}

.service-item {
  margin-bottom: 20px;
}

.service-header {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 5px 10px 5px 0;
  width: fit-content;
  border-radius: 10px;
  /*cursor: pointer;*/
}

/*.service-header:hover {*/
/*  background-color: #ececec;*/
/*  box-shadow: -10px 0 0 0 #ececec;*/
/*}*/

.description {
  padding: 0 15px;
}

.icon-arrow {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  transform: rotate(90deg);
  margin-left: 15px;
  transition: transform 0.2s ease;
}

.icon-arrow.rotated {
  transform: rotate(-90deg);
}
</style>
