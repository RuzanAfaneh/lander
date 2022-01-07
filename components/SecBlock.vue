<template>
  <div class="sec__container">
    <div
      class="sec__block"
      :class="isScrolledTo ? 'fade' : ''"
      v-on:scroll.native="handleScroll"
    >
      <h1 :class="isScrolledTo ? 'fade' : ''">
        Lorem ipsum dolor sit amet
      </h1>
      <div :class="isScrolledTo ? 'fade' : ''" class="sec__block-quote">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec
        odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla
        quis sem at nibh elementum imperdiet. Duis sagittis ipsum.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FirstBlock',
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
.sec__container {
  background-color: #ebe0cc;
  color: #9f9e9c;
  padding: 50px 0;
}

.sec__block {
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  max-width: 1000;
  width: 100%;
  text-align: center;

  h1 {
    font-weight: 600;
    color: #545454;
  }
}

.sec__block-quote {
  color: #9f9e9c;
  max-width: 500px;
}

.fade {
  animation: fadein 7s;
}

@keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
