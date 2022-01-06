<template>
  <div class="footer__container">
    <div class="footer__block">
      <div class="footer__item" v-for="({ url, title }, i) in items" :key="i">
        <a :href="url">{{ title }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ForthBlock',
  data() {
    return {
      items: [
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
        {
          title: 'Lorem ipsum dolor sit',
          url: '',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.footer__container {
  width: 100%;
  background: linear-gradient(-45deg, #b1a9a6, #d2d523);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  border-top: 10px solid red;
}

.footer__block {
  max-width: 1440px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  20% {
    background-position: 40% 20%;
  }
  40% {
    background-position: 20% 40%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.footer__item {
  cursor: pointer;
  flex-basis: 50%;
  margin: 20px 0;
  a {
    text-decoration: none;
  }
}
</style>
