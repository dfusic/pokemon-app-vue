<script setup>

const props = defineProps({
  pokemon: {
    type: Object,
    default: () => {},
  },
});
</script>

<template>
  <div className='single-pokemon'>
    <img :src='props.pokemon.image' alt="">
    <ul className='single-pokemon-list'>
  <li>{{props.pokemon.name}}</li>
  <li>{{props.pokemon.classfication}}</li>
  <li>{{props.pokemon.height_m}} m</li>
  <li>{{props.pokemon.hp}} HP</li>
  <li>{{props.pokemon.weight_kg}} kg</li>
 </ul>
  </div>
</template>

<style>
  .single-pokemon{
    display: flex;
    width: 300px;
    height: 150px;
    justify-content: center;
    align-items: center;
    padding: 16px;
    margin: 8px;
    font-family: Arial, Helvetica, Ubuntu, sans-serif;
    background-color: #eee;
    border-radius: 10px;
  }

  .single-pokemon > img{
    width: 100px;
  }
</style>
