<template>
  <div class="album col-lg-2 col-md-4 col-sm-6 col-12">
    <div class="box-img-album">
      <img :src="infoAlbum.poster" alt="">
    </div>
    <h1 class="title">{{infoAlbum.title}}</h1>
    <h4 class="author">{{infoAlbum.author}}</h4>
    <h5 class="year">{{infoAlbum.year}}</h5>
  </div>
</template>

<script>
export default {
   name: 'Album',
   props:{
     infoAlbum: Object
   },
}
</script>

<style lang="scss">

@import "../assets/scss/vars.scss";
@import "../assets/scss/mixin.scss";
@import "../assets/scss/utilities.scss";
@import "../assets/scss/generals.scss";

.album{
  background-color: $primary-color;
  width: 100%;
  margin: 20px 22px;
  text-align: center;
  padding: 15px!important;
  transition: 0.30s;
  cursor: pointer;
  box-shadow: 0 3px 3px rgba(black, $alpha: 0.3);
  &:hover{
    // filter: invert(1);
    transform: scale(105%);
    box-shadow: 0 3px 10px rgba(black, $alpha: 0.5);
  }
  .col-lg-2 {
    width: 14.666667%!important;
    };
  .box-img-album{
    width: 100%;
    padding-top: 100%;
    position: relative;
    overflow: hidden;
    img{
      position: absolute;
      top:0;
      left: 0;
      width: 100%;
    }
  }
  h1{
    margin: 20px 0;
    font-size: 23px;
    font-weight: 600;
  }
  h4{
    font-size: 18px;
  }
  h5{
    font-size: 15px;
    margin-bottom: 5px;
  }
}

</style>