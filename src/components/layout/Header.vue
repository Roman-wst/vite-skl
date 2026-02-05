<script setup>
defineProps({
  title: String,
})
</script>

<template>
  <header class="header">
    <div class="container">
      <div class="header__top d-flex">
        <img class="header__logo-sign" src="../../assets/svg/logo-skl-sign.svg" alt="Logo Skl sign">
        <div class="header__info">
          <img class="header__info-logo" src="../../assets/svg/logo-skl.svg" alt="Logo Skl full">
          <a href="tel:+79622532037">+7 962 253 20 37</a>
          <a href="mailto:sales@skillline.ru">sales@skillline.ru</a>
          <a href="https://skillline.ru/" target="_blank">skillline.ru</a>
        </div>
      </div>
      <div class="header__bottom">
        <h1>{{ title }}</h1>
      </div>      
    </div>
  </header>

</template>

<style scoped lang="scss">
.header {
  @include font(14, 18);
  padding-top: clmp(30, 60);
  padding-bottom: clmp(24, 48);
  background-color: $header-bg-color;
  color: $header-color;

  &__top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom: clmp(58, 116);
  }

  &__logo-sign {
    @include dim(84, 84);
  }

  &__info {
    font-family: $font-bold;
    display: flex;
    flex-direction: column;
    align-items: end;
    gap: rem(2);
    padding-left: rem(12)
  }

  &__info-logo {
    @include dim(120, 32);
    margin-bottom: rem(6);
  }

  a {
    color: $header-color;
  }
}



</style>
