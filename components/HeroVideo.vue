<template>
  <video class="hero_video" autoplay muted loop nocontrols>
    <source src="~/static/hero-video.mp4" type="video/mp4" />
  </video>
</template>

<script>
export default {
  name: 'HeroVideo',
}
</script>

<style lang="scss" scoped>
.hero_video {
  max-width: 100vw;
  min-height: 100vh;
  width: 100%;
  height: 100%;
}
</style>
