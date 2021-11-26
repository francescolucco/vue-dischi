<template>
   <div>
      <div v-if="loaded" class="row">
         <Album
            v-for="(album, index) in albums"
            :key="index"
            :infoAlbum = "album"
            />
      </div>
      <Loader v-else titleLoader="Dischi anni '70 '80 '90 '00"/>
   </div>
</template>

<script>

import Album from "./Album.vue";
import Loader from "./Loader.vue";
import axios from "axios";


export default {
   name: 'BoxAlbum',
   components: {
      Album,
      Loader
   },
   data(){
      return{
         urlApiBoolean: 'https://flynn.boolean.careers/exercises/api/array/music',
         albums: [],
         loaded: false
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