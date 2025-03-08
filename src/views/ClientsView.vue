<template>
  <div class="container">
    <h1 class="header-my-clients">Мои клиенты</h1>
    <div class="media-grid">
      <div
        v-for="(item, index) in mediaItems"
        :key="item.id"
        class="media-item"
        @click="openMedia(index)"
      >
        <span v-if="item.type === 'video'" class="icon-camera">
          <svg
            id="Layer_1"
            data-name="Layer 1"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="117 199 382 332"
            width="30px"
            height="30px"
          >
            <path
              fill="#fff"
              d="M482.28,434.61c-6.79,24.47-20.43,30.07-42.54,17.44-17.83-10.2-35.72-20.29-53.35-30.8a10.64,10.64,0,0,1-4.53-7.61q-.48-41.91,0-83.84a10.68,10.68,0,0,1,4.43-7.7c17.7-10.64,35.63-20.92,53.58-31.13,22-12.53,35.49-7,42.41,17.4Z"
            />
            <path
              fill="#fff"
              d="M234.59,481.24H154c-27,0-44.28-14.73-44.78-41.56-.89-46.78-.47-93.59.42-140.38.39-20.22,18.54-36.63,38.9-36.71q86.07-.36,172.15,0c22.53.11,39.62,18,39.66,40.64q.12,68.38,0,136.77c0,23.45-17.62,41.08-41.13,41.19C291,481.34,262.8,481.24,234.59,481.24Z"
            />
          </svg>
        </span>
        <img :src="item.preview" :alt="`Media ${index + 1}`" class="media-thumbnail" />
      </div>
    </div>

    <!-- Modal -->
    <div v-if="selectedMediaIndex !== null" class="media-modal" @click="closeMedia">
      <div class="media-modal-content" @click.stop>
        <template v-if="currentMedia">
          <img
            v-if="currentMedia.type === 'image'"
            :src="currentMedia.full"
            :alt="`Media ${selectedMediaIndex + 1}`"
          />
          <video v-else ref="videoRef" controls autoplay>
            <source :src="currentMedia.full" type="video/mp4" />
            Ваш браузер не поддерживает данный формат видео
          </video>
        </template>
        <button class="navigate-button left" @click="navigateMedia(-1)">&#8249;</button>
        <button class="navigate-button right" @click="navigateMedia(1)">&#8250;</button>
        <button class="close-button" @click="closeMedia">×</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, watch, computed } from 'vue'

interface MediaItem {
  id: number
  type: 'image' | 'video'
  preview: string
  full: string
}

import previewImage1 from '@/assets/media/ClientsView/clients-media/preview_images/client_image_1_small.jpg'
import previewImage2 from '@/assets/media/ClientsView/clients-media/preview_images/client_image_2_small.jpg'
import previewImage3 from '@/assets/media/ClientsView/clients-media/preview_images/client_image_3_small.jpg'
import previewImage4 from '@/assets/media/ClientsView/clients-media/preview_images/client_image_4_small.jpg'
import previewImage5 from '@/assets/media/ClientsView/clients-media/preview_images/client_image_5_small.jpg'

import image1 from '@/assets/media/ClientsView/clients-media/images/client_image_1.jpg'
import image2 from '@/assets/media/ClientsView/clients-media/images/client_image_2.jpg'
import image3 from '@/assets/media/ClientsView/clients-media/images/client_image_3.jpg'
import image4 from '@/assets/media/ClientsView/clients-media/images/client_image_4.jpg'
import image5 from '@/assets/media/ClientsView/clients-media/images/client_image_5.jpg'

import previewVideo1 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_1.jpg'
import previewVideo2 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_2.jpg'
import previewVideo3 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_3.jpg'
import previewVideo4 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_4.jpg'
import previewVideo5 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_5.jpg'
import previewVideo6 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_6.jpg'
import previewVideo7 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_7.jpg'
import previewVideo8 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_8.jpg'
import previewVideo9 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_9.jpg'
import previewVideo10 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_10.jpg'
import previewVideo11 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_11.jpg'
import previewVideo12 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_12.jpg'
import previewVideo13 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_13.jpg'
import previewVideo14 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_14.jpg'
import previewVideo15 from '@/assets/media/ClientsView/clients-media/preview_videos/preview_15.jpg'

import video1 from '@/assets/media/ClientsView/clients-media/videos/client_video_1.mp4'
import video2 from '@/assets/media/ClientsView/clients-media/videos/client_video_2.mp4'
import video3 from '@/assets/media/ClientsView/clients-media/videos/client_video_3.mp4'
import video4 from '@/assets/media/ClientsView/clients-media/videos/client_video_4.mp4'
import video5 from '@/assets/media/ClientsView/clients-media/videos/client_video_5.mp4'
import video6 from '@/assets/media/ClientsView/clients-media/videos/client_video_6.mp4'
import video7 from '@/assets/media/ClientsView/clients-media/videos/client_video_7.mp4'
import video8 from '@/assets/media/ClientsView/clients-media/videos/client_video_8.mp4'
import video9 from '@/assets/media/ClientsView/clients-media/videos/client_video_9.mp4'
import video10 from '@/assets/media/ClientsView/clients-media/videos/client_video_10.mp4'
import video11 from '@/assets/media/ClientsView/clients-media/videos/client_video_11.mp4'
import video12 from '@/assets/media/ClientsView/clients-media/videos/client_video_12.mp4'
import video13 from '@/assets/media/ClientsView/clients-media/videos/client_video_13.mp4'
import video14 from '@/assets/media/ClientsView/clients-media/videos/client_video_14.mp4'
import video15 from '@/assets/media/ClientsView/clients-media/videos/client_video_15.mp4'

const mediaItems = ref<MediaItem[]>([])
const selectedMediaIndex = ref<number | null>(null)
const videoRef = ref<HTMLVideoElement | null>(null)

onMounted(() => {
  document.title = 'Мои клиенты'

  mediaItems.value = [
    { id: 1, type: 'image', preview: previewImage1, full: image1 },
    { id: 2, type: 'image', preview: previewImage2, full: image2 },
    { id: 3, type: 'image', preview: previewImage3, full: image3 },
    { id: 4, type: 'image', preview: previewImage4, full: image4 },
    { id: 5, type: 'image', preview: previewImage5, full: image5 },
    { id: 6, type: 'video', preview: previewVideo1, full: video1 },
    { id: 7, type: 'video', preview: previewVideo2, full: video2 },
    { id: 8, type: 'video', preview: previewVideo3, full: video3 },
    { id: 9, type: 'video', preview: previewVideo4, full: video4 },
    { id: 10, type: 'video', preview: previewVideo5, full: video5 },
    { id: 11, type: 'video', preview: previewVideo6, full: video6 },
    { id: 12, type: 'video', preview: previewVideo7, full: video7 },
    { id: 13, type: 'video', preview: previewVideo8, full: video8 },
    { id: 14, type: 'video', preview: previewVideo9, full: video9 },
    { id: 15, type: 'video', preview: previewVideo10, full: video10 },
    { id: 16, type: 'video', preview: previewVideo11, full: video11 },
    { id: 17, type: 'video', preview: previewVideo12, full: video12 },
    { id: 18, type: 'video', preview: previewVideo13, full: video13 },
    { id: 19, type: 'video', preview: previewVideo14, full: video14 },
    { id: 20, type: 'video', preview: previewVideo15, full: video15 },
  ]
})

const openMedia = (index: number) => {
  selectedMediaIndex.value = index
}

const closeMedia = () => {
  selectedMediaIndex.value = null
}

const navigateMedia = (direction: number) => {
  if (selectedMediaIndex.value !== null) {
    const currentIndex = selectedMediaIndex.value
    selectedMediaIndex.value =
      (currentIndex + direction + mediaItems.value.length) % mediaItems.value.length
  }
}

const handleKeyDown = (event: KeyboardEvent) => {
  if (event.key === 'ArrowLeft') {
    navigateMedia(-1)
  } else if (event.key === 'ArrowRight') {
    navigateMedia(1)
  }
}

onMounted(() => {
  window.addEventListener('keydown', handleKeyDown)
})

onUnmounted(() => {
  window.removeEventListener('keydown', handleKeyDown)
})

// Watch for modal open/close to toggle body scrolling
watch(selectedMediaIndex, (newIndex) => {
  document.body.style.overflow = newIndex !== null ? 'hidden' : ''
})

// Watch for changes to selectedMediaIndex to update video playback
watch(selectedMediaIndex, (newIndex) => {
  if (videoRef.value && newIndex !== null) {
    const videoElement = videoRef.value
    videoElement.pause()
    videoElement.currentTime = 0
    videoElement.src = mediaItems.value[newIndex].full
    videoElement.load()
    videoElement.oncanplay = () => {
      videoElement.play()
    }
  }
})

const currentMedia = computed<MediaItem | null>(() =>
  selectedMediaIndex.value !== null ? mediaItems.value[selectedMediaIndex.value] : null,
)
</script>

<style scoped>
.container {
  max-width: 1100px;
  margin: 0 auto;
}
.header-my-clients {
  margin-left: 20px;
}
.media-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(162px, 1fr));
  gap: 30px;
  padding: 20px;
}
.media-item {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  cursor: pointer;
}
.media-thumbnail {
  width: 100%;
  height: 100%;
  display: block;
  border-radius: 8px;
}
.media-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}
.media-modal-content {
  position: relative;
  display: inline-block;
}
.media-modal-content :is(video, img) {
  width: auto;
  height: auto;
  max-width: 70vw;
  max-height: 90vh;
  display: block;
  margin: auto;
}
/* BUTTON STYLES */
button {
  padding: 0;
}
.navigate-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: white;
  font-size: 64px;
  cursor: pointer;
  z-index: 1001;
}
.navigate-button.left {
  left: -60px;
}
.navigate-button.right {
  right: -60px;
}
.close-button {
  position: absolute;
  top: 0;
  right: -50px;
  background: none;
  border: none;
  color: white;
  font-size: 44px;
  cursor: pointer;
  z-index: 1001;
}
.toMainPgBtn {
  margin-bottom: 20px;
}
.toMainPgBtn:hover {
  cursor: pointer;
  background-color: #dedede;
  outline: 3px solid #dedede;
  border-radius: 1px;
}
.icon-camera {
  position: absolute;
  left: 10px;
  top: 10px;
}
/* MEDIA QUERIES */
@media screen and (max-width: 434px) {
  .media-grid {
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  }

  .navigate-button.left {
    left: -35px;
  }

  .navigate-button.right {
    right: -35px;
  }
}

@media screen and (max-width: 1200px) {
  .leftArrow {
    left: 20%;
  }
  .rightArrow {
    right: 20%;
  }
}
</style>
