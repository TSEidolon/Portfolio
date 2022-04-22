<template>
<div class="hero-container-content">
  <div class="main-container">
  <!-- ---------------------------- -->
    <div class="text-container">
      <div id="border-container">
        <h4> Hello.  </h4>
        <h2> I am <span><strong> Edgar Caballero</strong> </span> </h2>
        <p> A Junior Web Developer with a love for all things science 
        </p>
      </div>
    </div>
  <!-- ------------------------------ -->
    <div class="socials-logo-container">
      <menu>
        <a href="https://github.com/TSEidolon" target="_blank" class="action" > <fa :icon="['fab', 'github']" class="GHIcon"/> </a>
        <a href="https://www.linkedin.com/in/edgar-francis-caballero-477556238/" target="_blank" class="action" > <fa :icon="['fab', 'linkedin']" class="LIIcon"/> </a>
        <a href="https://twitter.com/Eidolon_Parade" target="_blank" class="action" > <fa :icon="['fab', 'twitter']" class="TWIcon"/> </a>
        <a href="https://www.instagram.com/eidolon_parade/" target="_blank" class="action" > <fa :icon="['fab', 'instagram']" class="IGIcon"/> </a>
        <a href="#" class="trigger" > <fa :icon="['fas', 'plus']" class="PLIcon"/> </a>
      </menu>
    </div>
  </div>

</div>


</template>

<script setup>
import {onMounted} from 'vue'

onMounted (() => {
  const trigger = document.querySelector ("menu > .trigger");

  trigger.addEventListener('click', (e) => {
  e.currentTarget.parentElement.classList.toggle("open")
  });
})
  

</script>

<style>

/* Main Styles Start */
:root {
  --size: 4.5rem;
  --radius: 12rem;
  --padding: 1rem;
  --bg-color: #e0eaea;
  --fb-color: #116466;
  --hi-color: #FFCB9A;
  --dg-color: #2c3531;
}
.main-container {
  display: flex;
  position: relative;
  /* flex-wrap: wrap; */
  justify-content: space-between;
  align-items: center;
  gap: 7vw;
  height: 90vh;
  width: 100%;
  padding: 20% 10%;
}

@media (max-width:1000px){
  .main-container {
    flex-direction: column;
    justify-content: space-between;

    padding: 10% 5%;
}}
/* Main Styles End*/





/* Text Container Styles Start */
.text-container {
  height: 100%;
  min-height: 400px;
  width: 100%;
  max-width: 700px;
  
}

#border-container h4{
  font-size: 3rem;
}
#border-container h2{
  font-size: 4rem;
}
#border-container h2 span{
  /* color: var(--fb-color); */
  font-size: 5rem;
  color: #e2eeee;
  text-shadow: 1px 1px var(--fb-color);
}

#border-container p{
  font-size: 1.7rem;
}

#border-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  z-index: 0;
  border-radius: 10px;
  overflow: hidden;
  padding: 2rem;
  height: 100%;
  width: 100%;
  color: var(--bg-color);
  text-shadow: 2px 2px black;

}

#border-container:before {
    content: "";
    position: absolute;
    z-index: -2;
    left: -50%;
    top: -50%;
    width: 200%;
    height: 200%;
      background-image: conic-gradient(
        var(--bg-color),
        transparent 120deg
        );
    animation: rotate2 4s linear infinite;
  }

  #border-container:after {
    content: "";
    position: absolute;
    z-index: -1;
    left: 1%;
    top: 1%;
    width: 98%;
    height: 98%;
    background-color: var(--dg-color);
    border-radius: 5px;
  }

@keyframes rotate2 {
  100% {
    transform: rotate(-360deg);
  }
}

/* Text Container Styles End */

/* Social Logos Styles Start*/
.socials-logo-container {
  display: flex;
  justify-content: space-around;
  height: 600px;
  min-height: 400px;
  width: 600px;
  
  padding: 0.5rem;
  gap: 0.5rem; 
  
}

menu {
  display:flex;
  justify-content: center;
  align-items: center;
  position: relative;
  /* top: 20%;
  left: 25%; */
  height: 100%;
  min-height: 500px;
  width: 100%;
}

menu > * {
  position: absolute;
  display: grid;
  place-content: center;

  text-decoration: none;
  border-radius: 50%;
  color: var(--bg-color);
  box-shadow: 0px 0px 9px 0px var(--bg-color);
  font-size: 2.5rem;

}

menu > .action {
--factor: 0;

width: var(--size);
height: var(--size);
opacity: 0;


transform: rotate(calc(-1 * var(--angle))) translateY(calc(-1 * var(--radius) * var(--factor) )) rotate(var(--angle));
transition: 250ms ease-in-out;

}

menu > .action:hover, menu > .trigger:hover {
  color: var(--fb-color);
   box-shadow: 0px 0px 0px 0.35rem var(--bg-color);
}

.GHIcon:hover {
  color:grey;
}
.LIIcon:hover {
  color:rgb(60, 163, 197);
}
.TWIcon:hover {
  color:lightblue;
}
.IGIcon:hover {
  color:rgb(179, 120, 130);
}

menu.open > .action {
  --factor: 1;
  opacity: 1;
}

menu > .action:nth-child(1) {
  --angle: 0deg;
  transition-delay: 0ms;
}
menu > .action:nth-child(2) {
  --angle: 30deg;
  transition-delay: 50ms;
}
menu > .action:nth-child(3) {
  --angle: 60deg;
  transition-delay: 100ms;
}
menu > .action:nth-child(4) {
  --angle: 90deg;
  transition-delay: 150ms;
}

menu > .trigger {
  width: calc(1.6 * var(--size));
  height: calc(1.6 * var(--size));


  font-size: 4rem;
  transition: 250ms ease-in-out;
}

menu > .trigger > .PLIcon {
  transition: 250ms ease-in-out;
}

menu.open > .trigger > .PLIcon {
  transform: rotate(-135deg);
}

@media (max-width:1000px){
  menu {
  display:flex;
  justify-content: flex-start;
  align-items: flex-start;
  position: relative;
  }

.socials-logo-container {
  padding: 3rem;
 
  
}

  menu > .action {
  --radius: 12rem;
  
  transform: rotate(calc(-1 * var(--angle))) translateY(calc(0.8 * var(--radius) * var(--factor) )) rotate(var(--angle));
  transition: 250ms ease-in-out;}
}
/* Social Logos Styles End */



</style>