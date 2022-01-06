<template>
  <div
    class="seventh__container"
    style="background-size: cover"
    :class="hover ? 'seventh__container--hover' : ''"
    :style="[
      hover
        ? { background: 'url(' + bg + ') center no-repeat' }
        : { background: '#FFF' },
    ]"
  >
    <div class="block__title" :class="hover ? 'block__title--hover' : ''">
      Lorem ipsum dolor sit amet
    </div>
    <div>
      <div v-for="({ text, url, desc }, i) in items" :key="i">
        <div
          class="item__container"
          @mouseover="mouseOver(url, desc)"
          @mouseleave="hover = false"
        >
          <!-- <Light /> -->
          <span>{{ text }}</span>
        </div>
      </div>
    </div>
    <div class="item__desc" v-if="hover">{{ desc }}</div>
  </div>
</template>

<script>
// import Light from '../assets/light.svg'
// 
export default {
  name: 'SeventhBlock',
  components: {
    // Light,
  },
  data() {
    return {
      hover: false,
      bg: '#fff',
      desc: '',
      items: [
        {
          text: 'Lorem ipsum dolor sit',
          url: 'https://picsum.photos/id/233/3000/3000',
          desc: 'Sed cursus ante dapibus diam. Sed nisLorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. ',
        },
        {
          text: 'Lorem ipsum dolor sit',
          url: 'https://picsum.photos/id/237/3000/3000',
          desc: 'Praesent libero. Sed cursus ante dapibus diam. Sed nis',
        },
        {
          text: 'Lorem ipsum dolor sit',
          url: 'https://picsum.photos/id/236/3000/3000',
          desc: 'Lorem ipsum dolor sit amet,Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nis',
        },
        {
          text: 'Lorem ipsum dolor sit',
          url: 'https://picsum.photos/id/235/3000/3000',
          desc: 'consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nis',
        },
      ],
    }
  },
  methods: {
    mouseOver: function (lol, desc) {
      this.bg = lol
      this.hover = true
      this.desc = desc
    },
  },
}
</script>

<style lang="scss" scoped>
.seventh__container {
  align-items: center;
  animation: 0.2s bg forwards;
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 400px;
  position: relative;

  .block__title {
    color: black;
    font-size: 30px;
    font-weight: 600;
    margin-bottom: 30px;
    top: 10%;

    &--hover {
      color: white;
    }
  }

  > div {
    align-self: center;
    display: flex;
    justify-content: space-around;
    max-width: 1000px;
    position: absolute;
    top: 30%;
    width: 100%;
  }

  .item__desc {
    color: white;
    margin: 50px;
    position: absolute;
    text-align: center;
    top: 70%;
  }

  g,
  svg,
  path {
    fill: none;
    height: 70px;
    stroke: white;
    width: 70px;
  }

  &--hover {
    .item__container:not(:hover) {
      background: none;
      border: 1px solid white;
      color: white;

      span {
        display: none;
      }
    }
  }
}

.item__container {
  align-items: center;
  animation: 0.3s out ease forwards;
  background-color: #009ba6;
  border-radius: 50%;
  color: #009ba6;
  cursor: default;
  display: flex;
  flex-direction: column;
  height: 100px;
  justify-content: space-evenly;
  padding: 30px;
  text-align: center;
  width: 100px;

  &:hover {
    animation: 0.7s in forwards;
    background-color: white;

    g,
    svg,
    path {
      stroke: #009ba6;
    }
  }
}

@keyframes in {
  0% {
    opacity: 0;
    width: 100px;
    height: 100px;
  }

  20% {
    opacity: 0.3;
    width: 110px;
    height: 110px;
  }

  50% {
    opacity: 0.5;
    width: 115px;
    height: 115px;
  }

  100% {
    opacity: 0.7;
    width: 120px;
    height: 120px;
  }
}

@keyframes out {
  0% {
    width: 120px;
    height: 120px;
  }

  50% {
    width: 110px;
    height: 110px;
  }

  100% {
    width: 100px;
    height: 100px;
  }
}

@keyframes bg {
  0% {
    opacity: 0;
  }

  50% {
    opacity: 0.5;
  }

  100% {
    opacity: 1;
  }
}
</style>
