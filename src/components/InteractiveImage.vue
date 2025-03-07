<template>
  <div class="interactive-image" @click="openModal">
    <img :src="thumbnailSrc" :alt="altText" loading="lazy" class="thumbnail" />
  </div>
</template>

<script setup lang="ts">
defineProps({
  thumbnailSrc: {
    type: String,
    required: true,
  },
  fullSrc: {
    type: String,
    required: true,
  },
  altText: {
    type: String,
    default: 'Interactive image',
  },
})

const emit = defineEmits(['open-modal'])

const openModal = () => {
  emit('open-modal')
}
</script>
