<template>
  <div class="first__container">
    <div class="first__block" v-on:scroll.native="handleScroll">
      <img
        :class="isScrolledTo ? 'fade--left' : ''"
        src="https://picsum.photos/250/250"
      />
      <div :class="isScrolledTo ? 'fade--right' : ''">
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
.first__block {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 100px 70px;
  max-width: 1000px;
  margin: 0 auto;

  @media only screen and (max-width: 768px) {
    flex-wrap: wrap;
    padding: 20px;
  }

  > div,
  > p {
    flex-basis: 50%;
    font-family: 'Open Sans';

    @media only screen and (max-width: 768px) {
      flex-basis: 100%;
    }
  }
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
