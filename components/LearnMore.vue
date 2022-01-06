<template>
  <div class="learn-more__container">
    <h1
      class="learn-more__title"
      :class="hover ? 'learn-more__title--hover' : ''"
    >
      Lorem ipsum dolor sit amet
    </h1>
    <div class="lean-more__block">
      <div
        class="learn-more__item"
        @mouseover="hover = true"
        @mouseleave="hover = false"
        :style="{ backgroundImage: `url(${thumbnail})` }"
        v-for="({ text, thumbnail, desc }, i) in items"
        :key="i"
      >
        <div class="learn-more__text">{{ text }}</div>
        <div class="learn-more__desc">{{ desc }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ForthBlock',
  data() {
    return {
      hasScrolledToBottom: false,
      hover: false,

      items: [
        {
          text: 'Lorem ipsum dolor',
          thumbnail: 'https://picsum.photos/1000/1000',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. ',
        },
        {
          text: 'Lorem ipsum dolor',
          thumbnail: 'https://picsum.photos/1000/1000',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. ',
        },
        {
          text: 'Lorem ipsum dolor',
          thumbnail: 'https://picsum.photos/1000/1000',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. ',
        },
        {
          text: 'Lorem ipsum dolor',
          thumbnail: 'https://picsum.photos/1000/1000',
          desc: 'Lorrrrrrrem ipsum dolor sit amet, consectetur adipiscing elit. , Lorrrrem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. ',
        },
      ],
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
.learn-more__container {
  background-color: black;
  position: relative;

  .learn-more__title {
    display: block;
    position: absolute;
    text-align: center;
    top: 50%;
    width: 100%;
    z-index: 1;
    animation: fade-in 3s ease;
    &--hover {
      display: none;
    }
  }

  .lean-more__block {
    display: flex;
  }
}

.learn-more__item {
  background-repeat: no-repeat;
  animation: mesh-expand 0.3s forwards;
  flex-grow: 0;
  height: 250px;
  margin: 0 auto;
  max-height: 350px;
  overflow: hidden;
  position: relative;
  text-align: center;
  transform-origin: bottom;
  transition: width 1s ease;
  width: 25vw;

  div {
    margin: 0 20px;
    padding-top: 15px;
  }

  &::before {
    background-color: white;
    content: '';
    height: 40%;
    left: 10px;
    position: absolute;
    top: 5px;
    width: 3px;
  }

  .learn-more__desc {
    display: none;
    width: calc(30vw - 50px);
  }
}

.learn-more__item:hover {
  animation: expand 0.5s forwards;

  .learn-more__desc {
    display: block;
  }
}

@keyframes expand {
  0% {
    width: 25vw;
  }

  100% {
    width: 30vw;
  }
}

@keyframes mesh-expand {
  0% {
    width: 30vw;
  }

  100% {
    width: 25vw;
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }
  // 30% {
  //   opacity: 0.;
  // }
  100% {
    opacity: 1;
  }
}
</style>
