<script setup>

import {useAPI} from "../composables/useAPI";

const {movies, getMovies} = useAPI();

</script>

<template>
 

<div class="mt-18">
  <ul class="grid grid-cols-4 gap-10">
    <router-link class="p-3 bg-gray-400 rounded-md shadow-xl cursor-pointer hover:scale-125" v-for="movie in movies" :key="movies._id" :to="'/movie/${movie._id}'">
      <div>
        <h3 class="text-lg font-semibold">{{movie.name}}</h3>
        <p>Runtime:  {{movie.runtimeInMinutes}} Minutes</p>
        <p>Budget: ${{movie.budgetInMillions}} Million</p>
        <p>Revenue: ${{movie.boxOfficeRevenueInMillions}}</p>
        <p>Academy Wins: {{movie.academyAwardWins}}</p>
      </div>
    </router-link>
      

   
  </ul>


</div>

</template>