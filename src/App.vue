<template>
<div>
  <!--  -->
  <div class="object-area" >
    <ul class="objects">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div >
  <!--  -->
  <HeaderContainer />
  <HeroContainer />
  <SwiperContainer />
  <FooterContainer />
</div>
  
</template>

<script setup>
import SwiperContainer from './components/SwiperContainer.vue'
import HeroContainer from './components/HeroContainer.vue'
import HeaderContainer from './components/HeaderContainer.vue'
import FooterContainer from './components/FooterContainer.vue'

</script>

<style>
 @import url('https://fonts.googleapis.com/css2?family=PT+Sans+Narrow&display=swap');

/* App wide styling */
#app {
  font-family: 'PT Sans Narrow', sans-serif;
  /* background: radial-gradient(#116466, #2c3531); */
  background-color: #2c3531;

}

/* Resets */
*, *::before, *::after {
  box-sizing: border-box;
}

* {
  margin: 0;
}

html, body {
  height: 100%;
}
/*  */



/* TokyoWeb's Animated Background  */
.objects{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.objects li{
    position: absolute;
    display: block;
    list-style: none;
    width: 20px;
    height: 20px;
    background: rgba(255, 255, 255, 0.2);
    animation: animate 5s linear infinite;
    bottom: -150px;
    
}
.objects li:nth-child(1){
    left: 30%;
    width: 10px;
    height: 10px;
    animation-delay: 0s;
}
.objects li:nth-child(2){
    left: 10%;
    width: 20px;
    height: 20px;
    animation-delay: 2s;
    animation-duration: 6s;
}
.objects li:nth-child(3){
    left: 60%;
    width: 15px;
    height: 15px;
    animation-delay: 4s;
}
.objects li:nth-child(4){
    left: 80%;
    width: 10px;
    height: 10px;
    animation-delay: 0s;
    animation-duration: 9s;
}
.objects li:nth-child(5){
    left: 90%;
    width: 5px;
    height: 5px;
    animation-delay: 2s;
}


@keyframes animate {
    0%{
        transform: translateY(0) rotate(0deg);
        opacity: 1;
        border-radius: 50%;
    }
    100%{
        transform: translateY(-1000px) rotate(720deg);
        opacity: 0;
        border-radius: 100%;
    }

}
/*  */


</style>
