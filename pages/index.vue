<template>
  <div class="container">
    <HeroVideo />
    <FirstBlock />
    <SecBlock />
    <Block />
    <LearnMore />
    <IconsBlock />
    <BubblesBlock />
    <Footer />
  </div>
</template>

<script lang="ts">
import BubblesBlock from '../components/BubblesBlock.vue'
import FirstBlock from '../components/FirstBlock.vue'
import Footer from '../components/Footer.vue'
import Header from '../components/Header.vue'
import HeroVideo from '../components/HeroVideo.vue'
import IconsBlock from '../components/IconsBlock.vue'
import LearnMore from '../components/LearnMore.vue'
import Block from '../components/Block.vue'
import SecBlock from '../components/SecBlock.vue'
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  components: {
    Block,
    BubblesBlock,
    FirstBlock,
    Footer,
    Header,
    HeroVideo,
    IconsBlock,
    LearnMore,
    SecBlock,
  },
})
</script>

<style lang="scss">
.container {
  // max-width: 1440px;
  width: 100%;
  overflow: hidden;
  position: relative;
  font-family: 'Open Sans';
}

img {
  max-width: 100%;
  height: auto;
  margin: 0 auto;
}
</style>