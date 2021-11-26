<template>
  <header>
    <div class="box-logo">
      <img src="../assets/img/logo-spotify.png" alt="">
    </div>
    <div class="box-search"></div>
  </header>
</template>

<script>
export default {
   name: 'Header',
}
</script>

<style lang="scss">

@import "../assets/scss/vars.scss";
@import "../assets/scss/mixin.scss";
@import "../assets/scss/utilities.scss";
@import "../assets/scss/generals.scss";

  header{
    background-color: $primary-color;
    height: 70px;
    @include start();
    padding-left: 8px;
  }

</style>