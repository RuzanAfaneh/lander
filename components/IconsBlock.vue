<template>
  <div class="icons__container">
    <h1 class="title">Lorem Ipsum</h1>
    <!-- TODO: FOR LOOP -->
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
    <div><Light />Lorem ipsum dolor sit amet</div>
  </div>
</template>

<script>
import Light from '~/.nuxt/assets/light.svg'

export default {
  name: 'IconsBlock',
  components: {
    Light,
  },
  data() {
    return {
      hasScrolledToBottom: false,
    }
  },
  methods: {
    handleScroll: function (el) {
      this.hasScrolledToBottom = true
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll)
  },
}
</script>

<style lang="scss" scoped>
.icons__container {
  display: flex;
  width: 100%;
  flex-wrap: wrap;
      justify-content: space-evenly;


  h1 {
    flex-basis: 100%;
    align-items: center;
    justify-content: center;
    display: flex;
  }

  div {
    justify-content: space-evenly;
    display: flex;
    flex-direction: column;

    svg,
    path {
      width: 50px;
      height: 50px;
    }
    flex-basis: 26%;
  }
}
</style>
