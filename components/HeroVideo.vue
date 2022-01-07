<template>
  <div class="top">
    <Header />
    <video class="hero_video" autoplay muted loop nocontrols>
      <source
        src="https://video-previews.elements.envatousercontent.com/files/5ce7466f-36f6-48bc-b33d-01e5cba6c72f/video_preview_h264.mp4"
        type="video/mp4"
      />
    </video>
  </div>
</template>

<script>
import Header from './Header.vue'

export default {
  name: 'HeroVideo',
  components: {
    Header,
  }
}
</script>

<style lang="scss" scoped>
.top {
  position: relative;

}

.hero_video {
  height: auto;
  max-width: 100vw;
  width: 100%;
  z-index: -1;
}
</style>
