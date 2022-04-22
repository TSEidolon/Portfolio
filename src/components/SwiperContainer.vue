<template>
  <div class="swiper-container-main">
          <!-- :effect="'coverflow'"
      :grabCursor="true"
      :centeredSlides="true"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 200,
        modifier: 1,
        slideShadows: false,
      }" -->
    <swiper 

      :loop="true"
      :slidesPerView="3"
      :spaceBetween="20"
      :breakpoints="{
        1000: {
        slidesPerView: 3,
        spaceBetween: 30
        },
        600: {
        slidesPerView: 2,
        spaceBetween: 30
        },
        400: {
        slidesPerView: 1,
        spaceBetween: 10
        }
        }"
      
      :pagination="{
        clickable: true,
      }"
      :navigation="true"
      :modules="modules"
      class="mySwiper"
    >

      <swiper-slide>
       <div class="ui-card">
          <img src="../assets/images/vue-landing-page.png">
          <div class="description">
            <h3>ScalesEmporium Landing Page</h3>
            <p>A Landing page built using Vue 3</p>
            <a href="https://majestic-horse-ca27b9.netlify.app/" target="_blank">Explore More</a>
          </div>
        </div>
      </swiper-slide>
      <swiper-slide>
        <div class="ui-card">
          <img src="../assets/images/hoverboard.png">
          <div class="description">
            <h3>A Hoverboard Project</h3>
            <p>This project utilizes event listeners to paint each box a different color vie DOM manipulation</p>
            <a href="https://tseidolon.github.io/Hoverboard/" target="_blank">Explore More</a>
          </div>
        </div>
      </swiper-slide>
      <swiper-slide>
        <div class="ui-card">
          <img src="../assets/images/react-feedback-app.png">
          <div class="description">
            <h3>Feedback Application</h3>
            <p>This Feedback application was built using React. It utilizes the fundamentals of React (i.e. passing props, states, components, context) </p>
            <a href="https://feedback-app-tseidolon.netlify.app/" target="_blank">Explore More</a>
          </div>
        </div>
      </swiper-slide>
      <swiper-slide>
        <div class="ui-card">
          <img src="../assets/images/rest-api-fetch.png">
          <div class="description">
            <h3>Rest API</h3>
            <p>This project was built on Nuxt. Fetching data from an API (Hyrule Compendium API) using "useFetch" and "refreshNuxtData" to re-call and refresh the called data</p>
            <a href="https://extraordinary-sunshine-e41cf0.netlify.app/" target="_blank">Read More</a>
          </div>
        </div>
      </swiper-slide>

    </swiper>
  </div>
</template>

<script>


// Import Swiper Vue.js components

import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/effect-coverflow";
import "swiper/css/navigation";

// import required modules
import { Pagination, Navigation, EffectCoverflow } from "swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
 
  },
  setup() {
    return {
      modules: [Pagination, Navigation, EffectCoverflow],
    };
  },
};
</script>
<style>

/* .swiper-container-main {
  height: 100vh;
} */


.swiper-container-main {
  position: relative;  
  /* background: radial-gradient(#116466, #2c3531); */
  padding: 3rem 3rem;

  width: 100%;
  display: flex;
  align-items: center;
}

.swiper {
  width: 1300px;
  height: 600px;
  padding: 40px 10px;
  border: 2px solid #E0EAEA;
  border-radius: 10px;
  justify-content: center;
}




.swiper-slide {
  border-radius: 1rem;
  margin: 0;
  padding: 0;

  text-align: center;
  font-size: 18px;
  background: #fff;
  height: 100%;
  border: 1px solid #E0EAEA;



  /* Center slide text vertically */
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
}

.swiper-slide:hover {
  box-shadow: 0 3rem 6rem rgba(0, 0, 0, 0.4);
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;

}

.swiper-pagination{
  position: absolute;
}

.swiper-pagination-bullet{
  height: 7px;
  width: 26px;
  border-radius: 25px;
  background: #E0EAEA;
}

.swiper-button-next, .swiper-button-prev{
  opacity: 0.7;
  color: #E0EAEA;
  transition: all 0.3s ease;
}
.swiper-button-next:hover, .swiper-button-prev:hover{
  opacity: 1;
  color: #E0EAEA;
}


/* .button-51:before {
  background-color: #D5EDF6;
  content: "";
  height: calc(100% + 3px);
  position: absolute;
  right: -7px;
  top: -9px;
  transition: background-color 300ms ease-in;
  width: 100%;
  z-index: -1;
} */

.ui-card{
	width: 100%;
  height: 100%;
	position: relative;
	overflow: hidden;
	transition: all 0.3s ease-out;
	background:radial-gradient(#111 50%, #000 100%);
  border-radius: 1rem;

}

.ui-card img{
	/* transform: scale(1); */
	transition: all 0.3s ease-out;
  object-fit: cover;
}
.ui-card:hover img{
	transform: scale(1.1) translateY(-10px); 
	opacity: 0.3;
  
}
.ui-card .description{
	position: absolute;
	bottom: 0;
	left: 0;
	padding: 25px 0px;
	width: 100%;
	text-align: center;
	color: #E0EAEA;
	font-size: 18px;
}
.ui-card .description h3{
	font-weight: 700;
	font-size: 32px;
	margin: 0 0 20px;
	transform: translateY(30px);
	opacity: 0;
	transition: all 0.3s ease-out;

}
.ui-card .description p{
	transform: translateY(30px);
	opacity: 0;
  padding: 10px;
	transition: all 0.3s ease-out 0.2s;
}
.ui-card .description a{
	color: #E0EAEA;
	background:#116466;
  text-shadow: 1px 1px black;
	display: inline-block;
	padding: 10px 25px;
	border-radius: 5px;
	text-decoration: none;
	transform: translateY(30px);
	opacity: 0;
	transition: all 0.3s ease-in-out 0.4s;
}
.ui-card .description a:hover{
	background:#178688;
  word-spacing: 0.5rem;
}

.ui-card:hover .description h3{
	opacity: 1;
	transform: translateY(0px);
}
.ui-card:hover .description p{
	opacity: 1;
	transform: translateY(0px);
}
.ui-card:hover .description a{
	opacity: 1;
	transform: translateY(0px);
}



</style>