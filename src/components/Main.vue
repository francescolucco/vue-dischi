<template>
   <main>
      <div class="container">
         <!-- <h1>{{genreSelected}}</h1> -->
         <BoxAlbum
         :genreSelected="genreSelected"/>
      </div>
   </main>
</template>

<script>

import BoxAlbum from "./BoxAlbum.vue"

export default {
   name: 'Main',
   data(){
      return{
      }
   },
   props:{
      genreSelected: String,
   },
   methods: {
      bho(){
        console.log(this.genre);
      }
   },
   components:{
    BoxAlbum
   }
}
</script>

<style lang="scss">

@import "../assets/scss/vars.scss";
@import "../assets/scss/mixin.scss";
@import "../assets/scss/utilities.scss";
@import "../assets/scss/generals.scss";

main{
   padding: 100px 0;
   background-image: linear-gradient(to bottom,
   lighten($second-color, 0%),
   lighten($second-color, 50%),
   lighten($second-color, 50%),
   lighten($second-color, 0%));
   min-height: calc(100vh - 70px);
}

</style>