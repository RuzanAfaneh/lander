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
        :class="isScrolledTo ? 'in-buttom' : ''"
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
  name: 'LearnMore',
  data() {
    return {
      isScrolledTo: false,
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
.learn-more__container {
  background-color: black;
  position: relative;
  z-index: -2;

  @media only screen and (max-width: 768px) {
    background-color: white;
  }

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

    @media only screen and (max-width: 768px) {
      display: none;
    }
  }

  .lean-more__block {
    display: flex;

    @media only screen and (max-width: 768px) {
      flex-wrap: wrap;
    }
  }
}

.learn-more__item {
  align-items: center;
  background-color: white;
  background-repeat: no-repeat;
  display: flex;
  flex-direction: column;
  flex-grow: 0;
  height: 250px;
  margin: 0 auto;
  max-height: 350px;
  overflow: hidden;
  position: relative;
  text-align: center;
  transform-origin: bottom;
  transform: translatey(100%);
  transition: width 1s ease;
  width: 25vw;
  z-index: -1;

  @media only screen and (max-width: 768px) {
    width: 100vw;
    margin: 30px 0 0;

    &:last-child {
      margin-bottom: 30px;
    }
  }

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

    @media only screen and (max-width: 768px) {
      display: block;
      width: calc(100vw - 50px);
    }
  }
}

.learn-more__item:hover {
  width: 35vw;

  @media only screen and (max-width: 768px) {
    width: 100vw;
  }

  .learn-more__desc {
    display: block;
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes in-buttom {
  0% {
    transform: translatey(100%);
  }
  100% {
    transform: translatey(0);
  }
}

.in-buttom {
  animation: 3s in-buttom;
}

.learn-more__item:nth-child(1) {
  animation: 0.5s in-buttom forwards;
}

@for $i from 2 through 4 {
  .learn-more__item:nth-child(3n + #{$i}) {
    animation: 0.5s in-buttom forwards;
    animation-delay: $i - 1.5s;
  }
}
</style>
