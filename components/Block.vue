<template>
  <div class="third__container">
    <div
      class="third__blcok"
      :class="isScrolledTo ? 'fade' : ''"
      v-on:scroll.native="handleScroll"
    >
      <h1 class="third__block-title">
        Lorem ipsum dolor sit amet
      </h1>
      <div class="third__block-subtext">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec
        odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla
        quis sem at nibh elementum imperdiet. Duis sagittis ipsum.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Block',
  data() {
    return {
      isScrolledTo: false,
    }
  },
  methods: {
    handleScroll: function (el) {
      this.isScrolledTo = true
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
.third__container {
  background-image: url('https://picsum.photos/id/231/3000/3000');
  min-height: 450px;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.third__blcok {
  display: flex;
  justify-content: center;
  flex-direction: column;
  max-width: 1000px;
  margin: auto;
  padding: 50px 70px;
}

.third__block-title {
  color: white;
  font-weight: 600px;
  text-align: center;
}

.third__block-subtext {
  color: #939393;
  font-size: 24px;
  text-align: left;
}
</style>
