<script setup>

import {useAPI} from "../composables/useAPI";

const {movies,movie, getMovies} = useAPI();

movie.value = "";

</script>

<template>
 

<div class="mt-18">
  <ul class="grid grid-cols-4 gap-10">
    <router-link class="p-3 bg-gray-400 rounded-md shadow-xl cursor-pointer hover:scale-125" v-for="movie in movies" :key="movies._id" :to="'/movie/${movie._id}'">
      
    </router-link>
      

   
  </ul>


</div>

</template>