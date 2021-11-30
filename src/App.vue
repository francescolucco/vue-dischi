<template>
  <div>
    <Header 
    @changeGenre="sendgenere"/>
    <Main
    :genreSelected="genereSelected"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Main from "./components/Main.vue"

export default {
  name: 'App',
  data(){
    return{
      genereSelected: ''
    }
  },
  components: {
    Header, 
    Main,
  }, 
  methods:{
    sendgenere(genre){
      this.genereSelected = genre;
      console.log(this.genereSelected);
    }
  }
}
</script>

<style lang="scss">

@import './assets/scss/vars.scss';
@import './assets/scss/mixin.scss';
@import './assets/scss/generals.scss';
@import './assets/scss/utilities.scss';

</style>

