<script setup>

import { useRoute } from 'vue-router';
import { useAPI } from '../composables/useAPI';

const route = useRoute();

const {id} = route.params;

const {movie,quotes, getMovie,getQuote} = useAPI();

getMovie(id);
getQuote(id);

const who = async (id) => {
  const character = await getCharacter(id);
  console.log(character.name);
};

</script>

<template>
    <div v-if="movie" class="max-w-sm py-6 pt-10 mx-auto text-center bg-white rounded-md ">
        <h3 class="text-lg font-semibold">{{movie.name}}</h3>
        <p>Runtime:  {{movie.runtimeInMinutes}} Minutes</p>
        <p>Budget: ${{movie.budgetInMillions}} Million</p>
        <p>Revenue: ${{movie.boxOfficeRevenueInMillions}}</p>
        <p>Academy Wins: {{movie.academyAwardWins}}</p>
      </div>
      <div v-else>Loading.......</div>
      <div class="mt-8">
    <p
      class="px-6 py-8 my-4 text-lg italic text-center bg-white rounded-md"
      v-for="quote in quotes"
      :key="quote._id"
    >
      {{ quote.dialog }}
    </p>
  </div>
      </template>