<script setup>
import { defineProps } from 'vue';
import SinglePokemon from '../SinglePokemon/SinglePokemon.vue';

const props = defineProps({
  pokemonCategory: {
    type: Array,
    default: () => [],
  },
});

</script>

<template>
    <div className='pokemon-category'>
    <SinglePokemon
    v-for='(pokemon, index) in props.pokemonCategory'
    :key='index'
    :pokemon='pokemon'/>
    </div>
</template>

<style>
.pokemon-category{
    display: flex;
    flex-wrap: wrap;
}
</style>
