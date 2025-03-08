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
type ServiceKey = 'keratin' | 'nanoplastics' | 'coldRecovery' | 'hairCare'

interface Service {
  key: ServiceKey
  title: string
  description: string
}

const services: Service[] = [
  {
    key: 'keratin',
    title: 'Кератин / Ботокс',
    description:
      'Кератин - процедура помогает выпрямить волосы от лёгких волн до тугих завитков сроком от 3 до 6 месяцев. Ботокс - процедура помогает избавится от легкого пушка, разглаживает волосы, возможен легкий выпрямляющий эффект. Срок носки до 3х месяцев.',
  },
  {
    key: 'nanoplastics',
    title: 'Нанопластика',
    description:
      'Нанопластика - процедура помогает выпрямить самые тугие кудри. Выполняется исключительно на волосах хорошего качества! Не подходит для осветленных волос! Срок носки до 8 месяцев.',
  },
  {
    key: 'coldRecovery',
    title: 'Многоступенчатое холодное восстановление',
    description:
      'Максимально бережная процедура. Помогает восстановить волосы на молекулярном уровне, восстанавливает водный баланс и липидный слой. Обеспечивает внутриклеточную реконструкцию. После волосы блестящие, мягкие, плотные. Подходит беременным, кормящим и детям. Для сильно поврежденных волос требуется курс.',
  },
  {
    key: 'hairCare',
    title: 'Уход за натуральными и окрашенными волосами',
    description:
      'Процедура направлена на глубокое питание и увлажнение волоса. Дарит волосам природный блеск и ухоженный вид. Облегчает расчёсывание и укладку. Волосы становятся более плотными, эластичными и мягкими.',
  },
]
</script>

<style scoped>
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
}

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
