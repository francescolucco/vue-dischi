<template>
  <div class="loader text-center">
     <h1>{{titleLoader}}</h1>
     <h3>LOADING.....</h3>
     <div class="lds-ripple"><div></div><div></div></div>
  </div>
</template>

<script>
export default {
   name:'Loader',
   props:{
      titleLoader: String
   }

}
</script>

<style lang="scss">

@import "../assets/scss/vars.scss";
@import "../assets/scss/mixin.scss";
@import "../assets/scss/utilities.scss";
@import "../assets/scss/generals.scss";

.loader{
   @include center();
   padding-top: 25%;
   flex-direction: column;
   h1{
      margin-bottom: 150px;
   }
   .lds-ripple {
      display: inline-block;
      position: relative;
      width: 80px;
      height: 80px;
      }
      .lds-ripple div {
      position: absolute;
      border: 4px solid #fff;
      opacity: 1;
      border-radius: 50%;
      animation: lds-ripple 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
      }
      .lds-ripple div:nth-child(2) {
      animation-delay: -0.5s;
      }
      @keyframes lds-ripple {
      0% {
         top: 139px;
         left: -76px;
         width: 0;
         height: 0;
         opacity: 1;
      }
      100% {
         top: 0px;
         left: 0px;
         width: 140px;
         height: 140px;
         opacity: 0;
      }
   }
}

</style>