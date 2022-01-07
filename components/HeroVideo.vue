<template>
  <video class="hero_video" autoplay muted loop nocontrols>
    <source
      src="https://video-previews.elements.envatousercontent.com/files/5ce7466f-36f6-48bc-b33d-01e5cba6c72f/video_preview_h264.mp4"
      type="video/mp4"
    />
  </video>
</template>

<script>
export default {
  name: 'HeroVideo',
}
</script>

<style lang="scss" scoped>
.hero_video {
  height: auto;
  max-width: 100vw;
  width: 100%;
}
</style>
