<template>
  <div class="icons__container">
    <div class="icons__block">
      <h1 class="icons__title">Lorem Ipsum</h1>
      <div
        class="icons__item"
        :class="hasScrolledToBottom ? 'fade-in' : ''"
        v-for="({ text }, i) in items"
        :key="i"
      >
        {{ text }}
      </div>
    </div>
  </div>
</template>

<script>
// import Light from '~@assets/light.svg'

export default {
  name: 'IconsBlock',
  components: {
    // Light,
  },
  data() {
    return {
      items: [
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
        {
          text: 'Lorem ipsum dolor sit',
          icon: '',
        },
      ],
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
@import url('https://use.fontawesome.com/releases/v5.13.0/css/all.css');

.icons__container {
  background-color: #ebe0cc;

  .icons__title {
    flex-basis: 100%;
    align-items: center;
    justify-content: center;
    display: flex;
  }

  .icons__block {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    margin: 0 auto;
    max-width: 1000px;
    padding: 30px;
    width: 100%;

    @media only screen and (max-width: 768px) {
    padding: 20px;
    }
  }

  div {
    align-items: center;
    color: black;
    display: flex;
    justify-content: space-evenly;
    position: relative;
    flex-basis: 26%;

    @media only screen and (max-width: 768px) {
      flex-basis: 100%;
    }

    svg,
    path {
      width: 50px;
      height: 50px;
    }
  }

  .icons__item {
    opacity: 0;
    padding: 30px 20px;
    flex-direction: column;
    align-items: flex-start;

    &::before {
      content: '\f35a';
      font-family: 'Font Awesome 5 Free';
      font-style: normal;
      font-weight: normal;
      font-size: 40px;
      color: #009ba6;
      margin-bottom: 10px;
    }
  }
}

@keyframes fade {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

$couner: 0s;

@for $i from 2 through 10 {
  $couner: $couner + 0.4s;
  .fade-in:nth-child(#{$i}) {
    animation: 0.5s fade forwards;
    animation-delay: $couner;
  }
}
</style>
