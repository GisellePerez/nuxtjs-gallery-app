<template>
  <div>
    <h1>{{ pokemon.title }}</h1>
    <p>{{ pokemon.description }}</p>

    <!-- <hr />
    POKEMON =====
    {{ JSON.stringify(pokemon) }}
    <hr />

    <hr />
    COSO =====
    {{ JSON.stringify(coso) }}
    <hr /> -->
  </div>
</template>

<script setup>
const categoryRef = ref();

const { id } = useRoute().params;
const pokemonUrl = `https://fakestoreapi.com/products/${id}`;

// Fetch pokemon data
const { data: pokemon, pending } = await useFetch(pokemonUrl, { key: id })

const { data: coso, execute, refresh } = await useAsyncData(
  'coso',
  () => $fetch(`https://fakestoreapi.com/products/category/${pokemon.category}`, {
    params: {
      pokemon: pokemon.category
    }
  }),
  {
    immediate: false,
    watch: [categoryRef],
  },
);

</script>

<style lang="scss" scoped>
  
</style>
