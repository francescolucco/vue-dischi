<template>
   <div>
      <div v-if="loaded" class="row">
         <Album
            v-for="(album, index) in filteredAlbum"
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
   props:{
      genreSelected: String,
   },
   data(){
      return{
         urlApiBoolean: 'https://flynn.boolean.careers/exercises/api/array/music',
         albums: [],
         loaded: false,
      }
   },
   methods:{
      getApi(){
         axios.get(this.urlApiBoolean)
            .then(response =>{
               this.albums = response.data.response;
               console.log(this.albums);
               this.loaded = true;
            })
            .catch(error =>{
               console.log(error);
            });
         },
      },

   computed:{
      filteredAlbum(){
         if(this.genreSelected === 'selected' || this.genreSelected === ''){
            return this.albums;
         }
         // return this.albums.filter(album => album.genre === this.genreSelected)
         const discFiltered = [];

         this.albums.forEach(album =>{
            if(album.genre === this.genreSelected){
               discFiltered.push(album);
            }
         })
         console.log(discFiltered);
         return discFiltered;
         
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