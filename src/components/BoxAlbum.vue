<template>
   <div class="row">
      <Album
         v-for="(album, index) in albums"
         :key="index"
         :infoAlbum = "album"
         />
   </div>
</template>

<script>

import Album from "./Album.vue";
import axios from "axios";


export default {
   name: 'BoxAlbum',
   components: {
      Album
   },
   data(){
      return{
         urlApiBoolean: 'https://flynn.boolean.careers/exercises/api/array/music',
         albums: [],
      }
   },
   methods:{
      getApi(){
         axios.get(this.urlApiBoolean)
            .then(response =>{
               this.albums = response.data.response;
               console.log(this.albums);
            })
         
      }
   },
   mounted(){
      this.getApi();
   }
}
</script>

<style lang="scss">

@import "../assets/scss/vars.scss";
@import "../assets/scss/mixin.scss";
@import "../assets/scss/utilities.scss";
@import "../assets/scss/generals.scss";

.row{
   @include wrap();
}

</style>