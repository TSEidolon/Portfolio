<template>
  <div class="card-container-body">
    <div class="products-area">
      <h1>Check Out Our Pets Below:</h1>
    </div>
    <div class="card-container">
      <CardContainerContent 
      v-for="x in products" :key="x.id" :title="x.title" :bgtext="x.bgtext" :button="x.button" :src="x.src"
      >
      {{x}}
      </CardContainerContent>

    </div>
  </div>
</template>

<script setup>
import CardContainerContent from './CardContainerContent.vue';

const products = ([
        {
          title: 'Lizards',
          button: 'More',
          bgtext: 'Browse all Lizards, reptile food, and supplies.',
          src: require('../../assets/images/logo.png'),
        },
        {
          title: 'Lizards',
          button: 'More',
          bgtext: 'Browse all Lizards, reptile food, and supplies.',
          // src: require('../assets/images/lizard2.jpg'),
        },
 
])
</script>

<style>
:root {
  --primary-color:  #D5E5E4; /* green 100*/
  --secondary-color: #050D0C; /* green 900*/
  --tertiary-color:  #235F5A; /* green 600*/
  --quaternary-color: #173F3C; /* green 700*/
}
.products-area h1 {
  font-size: 3rem;
  padding: 1rem;
  margin-top: 3rem;
  color: var(--primary-color);
}
.card-container-body {
  display:flex;
  flex-direction: column;
  align-items: center;
  justify-items: center;
  text-align: center;
  padding: 1rem 1rem 0 1rem;
  gap: 1rem;

  background-color: var(--quaternary-color);
  text-shadow: 3px 6px 4px rgba(0, 0, 0, 0.15);
  height: 100%;
  position: relative;
}
 .card-container {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 1.5rem;
border: 1rem;

}

.products-area-logo {
width: 100px;
margin-top: 1rem;
margin-bottom: 3rem;
}


</style>