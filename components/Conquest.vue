<template>
  <div class="rounded-lg overflow-hidden">
    <SlidevVideo
        id="conquest-video"
        class="w-full duration-400 ease-out transition"
        muted
        autoreset="click"
        v-motion
        :initial="{ scale: 1, y: 0, x: 0, }"
        :click-3="{ scale: 3.6, y: 468, x: 0, transition: { type: 'tween'}}"
        :click-7="{ scale: 1, y: 0, x: 0, transition: { type: 'tween'} }"
        :click-8="{ scale: 3, y: -190, x: -600, transition: { type: 'tween'} }"
        :click-10="{ scale: 1, y: 0, x: 0, transition: { type: 'tween'} }"
        :style="{ borderRadius: '0.5rem' }"
        loop
    >
      <source src="/assets/3/conquest.mp4" type="video/mp4" />
    </SlidevVideo>
  </div>
</template>
<script setup lang="ts">
import {onMounted, ref, watch} from "vue";

const props = defineProps<{
  clicks: number
}>()

function handleStep(step: number) {
  const video = document.getElementById('conquest-video') as HTMLVideoElement;
  if(video) {
    if(window.location.pathname.includes('presenter')) {
      steps.value[step - 1]?.(video)
      return;
    }
    steps.value[step]?.(video)
  }
}

onMounted(() => {
  handleStep(props.clicks ?? 0)
})

watch(() => props.clicks, (newVal) => {
  handleStep(newVal)
})

const fadeOutTimeoutId = ref<number | null>(null);
const fadeInTimeoutId = ref<number | null>(null);

function loopVideoUpgradeFragment(event: Event) {
  const video = event.target as HTMLVideoElement;
  if(video.currentTime >= 17.2) {
    video.currentTime = 14.6
  }
}

const steps = ref([
  (video: HTMLVideoElement) => {
    video.pause()
  },
  (video: HTMLVideoElement) => {
    video.currentTime = 0;
    video.play()
    video.style.opacity = '100%'
    video.playbackRate = 1
    clearTimeouts()
  },
  (video: HTMLVideoElement) => {
    video.style.opacity = '0%'
    fadeOutTimeoutId.value = window.setTimeout(() => {
      video.currentTime = 16.9
      video.playbackRate = 0.5
      video.play()
      video.style.opacity = '100%'
      fadeInTimeoutId.value = window.setTimeout(() => {
        video.pause()
      }, 1800)
    }, 400)
  },
  (video: HTMLVideoElement) => {
    video.pause()
    video.currentTime = 17.75
    clearTimeouts()
  },
  (video: HTMLVideoElement) => {
    video.pause()
    video.currentTime = 17.75
  },
  (video: HTMLVideoElement) => {
    video.pause()
    video.currentTime = 17.75
  },
  (video: HTMLVideoElement) => {
    clearTimeouts()
    video.pause()
    video.currentTime = 17.75
  },
  (video: HTMLVideoElement) => {
    video.style.opacity = '0%'
    fadeOutTimeoutId.value = window.setTimeout(() => {
      video.play()
      video.currentTime = 14.6
      video.playbackRate = 0.5
      video.style.opacity = '100%'
      fadeInTimeoutId.value = window.setTimeout(() => {
        video.pause()
      }, 5300)
    }, 400)
  },
  (video: HTMLVideoElement) => {
    clearTimeouts()
    video.pause()
    video.currentTime = 17.2
    video.playbackRate = 0.5
    video.removeEventListener('timeupdate', loopVideoUpgradeFragment)
  },
  (video: HTMLVideoElement) => {
    clearTimeouts()
    video.currentTime = 14.6
    video.playbackRate = 0.5
    video.addEventListener('timeupdate', loopVideoUpgradeFragment)
    video.play()
  },
  (video: HTMLVideoElement) => {
    video.removeEventListener('timeupdate', loopVideoUpgradeFragment)
    video.play()
    video.playbackRate = 1
  }
])

const clearTimeouts = () => {
  if(fadeOutTimeoutId.value) {
    clearTimeout(fadeOutTimeoutId.value)
    fadeOutTimeoutId.value = null
  }
  if(fadeInTimeoutId.value) {
    clearTimeout(fadeInTimeoutId.value)
    fadeInTimeoutId.value = null
  }
}
</script>
