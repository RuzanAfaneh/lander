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
  background: linear-gradient(-45deg, #587bdb, #10063f);
  background-size: 400% 400%;
  animation: gradient 5s ease infinite;
  border-top: 5px solid red;
}

.footer__block {
  max-width: 1000px;
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;
  padding: 20px;

  .footer__item {
    cursor: pointer;
    flex-basis: 50%;
    margin: 20px 0;

    a {
      color: white;
      text-decoration: none;
    }
  }
}

@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
