<template>
  <div class="first__container">
    <div class="first__block" v-on:scroll.native="handleScroll">
      <img
        :class="hasScrolledToBottom ? 'fade--left' : ''"
        src="https://picsum.photos/250/250"
      />
      <div :class="hasScrolledToBottom ? 'fade--right' : ''">
        <h1>Lorem Ipsum</h1>
        <h2>Our Vision</h2>
        <p>
          Accountable leadership for exceptional healthcare in KSA and beyond
        </p>
        <h2>Our Mission</h2>
        <p>
          Unleashing individual and collective leadership potential to achieve
          better health and care
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FirstBlcok',
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
.first__container {

}

.first__block {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 100px 70px;
  max-width: 1000px;
  margin: 0 auto;
  > div,
  > p {
    flex-basis: 50%;
  }
}
.fade {
  background-color: red;
}

@keyframes in-left {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(0);
  }
}

@keyframes in-right {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0);
  }
}

.fade--right {
  animation: 3s in-right;
}

.fade--left {
  animation: 3s in-left;
}
</style>
