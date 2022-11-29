<script setup>
import { ref, watch } from 'vue';
import PokemonCategory from './components/PokemonCategory/PokemonCategory.vue';
import PokemonDropdown from './components/PokemonDropdown/PokemonDropdown.vue';
import pokemons from '../pokemon.json';

console.log({ pokemons });

const pokemonCategories = ref(Object.keys(pokemons));
const selectedPokemonCategory = ref(pokemons.grass);
const selectedPokemonCategoryName = ref(Object.keys(pokemons)[0]);

const handlePokemonCategorySelect = (event) => {
  selectedPokemonCategoryName.value = event.target.value;
};

watch(selectedPokemonCategoryName, (newValue) => {
  selectedPokemonCategory.value = pokemons[newValue];
});

console.log(selectedPokemonCategory.value);

</script>

<template>
  <div>
    <h1>Pokemon app</h1>
    <PokemonDropdown
      :categories='pokemonCategories'
      :selectHandler='handlePokemonCategorySelect'
    />
    <PokemonCategory
    :pokemonCategory='selectedPokemonCategory' />
  </div>
</template>

<style>
  html, body{
    padding: 0;
    margin: 0;
  }
</style>
