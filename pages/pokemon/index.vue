<template>
  <div>
    <h2>pokemon list</h2>

    <section class="cards-grid">
      <div v-for="p in posts">
        <!-- <NuxtLink :to="`/pokemon/${p.id}`">
          {{ p.title }}
        </NuxtLink> -->
        <!-- <PokemonCard :pokemon="p" /> -->
      </div>
    </section>
  </div>

  COSO:
  <pre>{{ coso }}</pre>
</template>

<script setup>
// Fetch data
const { data: posts } = await useFetch('https://jsonplaceholder.typicode.com/posts');
// const { data: pokemonList } = await useFetch('https://pokeapi.co/api/v2/pokemon?limit=25');
const pokemonList = {
  count: 1281,
  next: 'https://pokeapi.co/api/v2/pokemon?offset=25&limit=25',
  previous: null,
  results: [
    {
      name: 'bulbasaur',
      url: 'https://pokeapi.co/api/v2/pokemon/1/',
    },
    {
      name: 'ivysaur',
      url: 'https://pokeapi.co/api/v2/pokemon/2/',
    },
    {
      name: 'venusaur',
      url: 'https://pokeapi.co/api/v2/pokemon/3/',
    },
    {
      name: 'charmander',
      url: 'https://pokeapi.co/api/v2/pokemon/4/',
    },
    {
      name: 'charmeleon',
      url: 'https://pokeapi.co/api/v2/pokemon/5/',
    },
    {
      name: 'charizard',
      url: 'https://pokeapi.co/api/v2/pokemon/6/',
    },
    {
      name: 'squirtle',
      url: 'https://pokeapi.co/api/v2/pokemon/7/',
    },
    {
      name: 'wartortle',
      url: 'https://pokeapi.co/api/v2/pokemon/8/',
    },
    {
      name: 'blastoise',
      url: 'https://pokeapi.co/api/v2/pokemon/9/',
    },
    {
      name: 'caterpie',
      url: 'https://pokeapi.co/api/v2/pokemon/10/',
    },
    {
      name: 'metapod',
      url: 'https://pokeapi.co/api/v2/pokemon/11/',
    },
    {
      name: 'butterfree',
      url: 'https://pokeapi.co/api/v2/pokemon/12/',
    },
    {
      name: 'weedle',
      url: 'https://pokeapi.co/api/v2/pokemon/13/',
    },
    {
      name: 'kakuna',
      url: 'https://pokeapi.co/api/v2/pokemon/14/',
    },
    {
      name: 'beedrill',
      url: 'https://pokeapi.co/api/v2/pokemon/15/',
    },
    {
      name: 'pidgey',
      url: 'https://pokeapi.co/api/v2/pokemon/16/',
    },
    {
      name: 'pidgeotto',
      url: 'https://pokeapi.co/api/v2/pokemon/17/',
    },
    {
      name: 'pidgeot',
      url: 'https://pokeapi.co/api/v2/pokemon/18/',
    },
    {
      name: 'rattata',
      url: 'https://pokeapi.co/api/v2/pokemon/19/',
    },
    {
      name: 'raticate',
      url: 'https://pokeapi.co/api/v2/pokemon/20/',
    },
    {
      name: 'spearow',
      url: 'https://pokeapi.co/api/v2/pokemon/21/',
    },
    {
      name: 'fearow',
      url: 'https://pokeapi.co/api/v2/pokemon/22/',
    },
    {
      name: 'ekans',
      url: 'https://pokeapi.co/api/v2/pokemon/23/',
    },
    {
      name: 'arbok',
      url: 'https://pokeapi.co/api/v2/pokemon/24/',
    },
    {
      name: 'pikachu',
      url: 'https://pokeapi.co/api/v2/pokemon/25/',
    },
  ],
};

const { data: coso, pending, error, refresh } = await useAsyncData(
  'asdas',
  () => $fetch(`https://jsonplaceholder.typicode.com/posts/${posts[0].id}`)
)






</script>

<style scoped>
.cards-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 1rem;
}
</style>
