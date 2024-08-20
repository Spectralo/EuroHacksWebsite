<script setup>
import { ref } from "vue";
import countries from "../data/cards.json";
console.log(countries);

let width = 20;
let countriesLength = countries.length;

const cssvars = ref({
  ContainerWidth: width * countriesLength + "vw",
  CardWidth: width + "vw",
  AnimWidth: width * countriesLength,
});
</script>

<template>
  <div class="carousel">
    <div class="carouselcards" v-for="item in countries">
      <p>{{ item.countryName }}</p>
    </div>
    <div class="carouselcards" v-for="item in countries">
      <p>{{ item.countryName }}</p>
    </div>
  </div>
</template>

<style>
.carousel {
  display: flex;
  flex-direction: row;
  width: v-bind("cssvars.ContainerWidth");
}

.carouselcards {
  height: 20vh;
  width: v-bind("cssvars.CardWidth");
  background-color: red;
  animation: scroll 10s linear infinite;
  overflow: hidden;
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(v-bind("cssvars.AnimWidth")));
  }
}
</style>
