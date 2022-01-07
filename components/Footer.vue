<template>
  <div class="footer__container">
    <div class="footer__block">
      <span class="footer__item" v-for="({ url, title }, i) in items" :key="i">
        <a :href="url">{{ title }}</a>
      </span>
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
  animation: gradient 5s ease infinite;
  background-size: 400% 400%;
  background: linear-gradient(-45deg, #587bdb, #10063f);
  border-top: 5px solid red;
  width: 100%;
}

.footer__block {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
  margin: 0 auto;
  max-width: 1000px;
  padding: 20px 70px;

  @media only screen and (max-width: 768px) {
    padding: 20px 10px;
  }

  .footer__item {
    cursor: pointer;
    flex-basis: 50%;
    margin: 20px 0;

    @media only screen and (max-width: 768px) {
      flex-basis: 100%;
      display: flex;
      justify-content: center;
    }

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
