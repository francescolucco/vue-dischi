<template>
   <main>
      <div class="container">
         <BoxAlbum/>
      </div>
   </main>
</template>

<script>

import BoxAlbum from "./BoxAlbum.vue"

export default {
   name: 'Main',
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
   background-color: $second-color;
   min-height: calc(100vh - 70px);
}

</style>