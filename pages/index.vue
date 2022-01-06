<template>
  <div class="container">
    <HeroVideo />
    <FirstBlock />
    <SecBlock />
    <Block />
    <LearnMore />
    <SeventhBlock />
    <IconsBlock />
    <Footer />
  </div>
</template>

<script lang="ts">
import Block from '../components/Block.vue'
import FirstBlock from '../components/FirstBlock.vue'
import Footer from '../components/Footer.vue'
import HeroVideo from '../components/HeroVideo.vue'
import IconsBlock from '../components/IconsBlock.vue'
import LearnMore from '../components/LearnMore.vue'
import SecBlock from '../components/SecBlock.vue'
import SeventhBlock from '../components/SeventhBlock.vue'
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  components: {
    HeroVideo,
    FirstBlock,
    SecBlock,
    Block,
    IconsBlock,
    Footer,
    LearnMore,
    // SeventhBlock,
  },
})
</script>

<style lang="scss">
.container {
  // max-width: 1440px;
  width: 100%;
}

body
{
  margin: 0;
}
</style>