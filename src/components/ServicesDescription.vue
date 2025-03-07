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
    key: 'pealing',
    title: 'Пилинг',
    description:
      'С помощью этой процедуры можно удалить омертвевшие клетки с поверхности кожи, которые мешают ей дышать и делают ее тусклой и «уставшей». Кроме того, такое очищение способствует лучшему проникновению питательных веществ в глубокие слои кожи, что способствует более эффективному уходу за ней.',
  },
  {
    key: 'keratin',
    title: 'Кератиновое выпрямление',
    description:
      'Кератиновое выпрямление волос используется для укрепления и разглаживания волос, снижения пушистости, улучшения их текстуры и придания сияния. Это процедура, во время которой на волосы наносится специальный состав, содержащий кератин – протеин, который составляет основу волос. После обработки волосы становятся более прямыми, сияющими и легкими в укладке. Кератиновое выпрямление также помогает предотвратить сечение кончиков, защищает волосы от воздействия вредных факторов окружающей среды и увлажняет их.',
  },
  {
    key: 'botox',
    title: 'Ботокс для волос',
    description:
      'Ботокс для волос особенно подходит для тех, кто сталкивается с сухостью, ломкостью, отсутствием объема, повышенной электризацией или выпадением волос.',
  },
  {
    key: 'coldRecovery',
    title: 'Холодное восстановление',
    description:
      'Холодное восстановление волос — это процедура, направленная на восстановление повреждённых, секущихся, тусклых и тонких прядей. Она помогает реконструировать защитную оболочку волоса, улучшая его структуру и внешний вид.',
  },
  {
    key: 'nanoplastics',
    title: 'Нанопластика',
    description:
      'Это современная процедура, направленная на выпрямление и оздоровление волос с использованием органических кислот и натуральных компонентов. Основная цель нанопластики — сделать волосы прямыми, гладкими и блестящими, а также восстановить их структуру и укрепить изнутри.',
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
