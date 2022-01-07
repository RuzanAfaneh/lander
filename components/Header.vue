<template>
  <header class="header__conianter">
    <div>
      <button class="header__button log">Log In</button>
      <button class="header__button sign">Sign Up</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
@import 'https://fonts.googleapis.com/css?family=Open+Sans:300,400,600,700';

.header__conianter {
  align-items: center;
  background-color: transparent;
  border-bottom: 1px solid white;
  display: flex;
  height: 70px;
  justify-content: end;
  padding: 10px;
  position: absolute;
  top: 0;

  > div {
    width: 1000px;
  }
}

.header__button {
  width: 100px;
  height: 50px;
  margin: auto 20px;
  color: white;
  font-weight: 600;
  font-family:  'Open Sans';
  border-radius: 10px;
  text-transform: uppercase;
}

.log {
  background-color: transparent;
  border: 1px solid white;
}

.sign {
  background-color: #212121;
  border: none;
}
</style>
