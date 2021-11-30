<template>
  <header>
    <div class="box-logo">
      <img src="../assets/img/logo-spotify.png" alt="">
    </div>
    <div class="box-search">
      <select 
        class="form-select" 
        v-model="genre"
        @change="$emit('changeGenre', genre)"
        aria-label="Default select example">
        <option value="selected" selected>Seleziona il genere musicale</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="Rock">Rock</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
   name: 'Header',
   data(){
     return{
       genre: '',
   }
  },
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
    @include between();
    padding-left: 8px;
    padding-right: 60px;
      .form-select {
      display: inline-block;
      width: 300px !important;
   }
  }

</style>