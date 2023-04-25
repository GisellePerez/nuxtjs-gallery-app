<template>
  <!-- <div class="card"> -->
  <NuxtLink :to="`/pokemon/${pokemon.id}`" class="card-link">
    <v-card @click="test" class="card">
      <div class="card-img-wrapper">
        <img
          class="card-img"
          :src="pokemon.sprites.front_default"
          :alt="pokemon.name"
        />
      </div>

      <div class="card-data">
        <h3 class="title">{{ pokemon.name }}</h3>

        <!-- Type chips -->
        <div class="chips-wrapper">
          <div v-for="t in pokemon.types" class="chip">
            <p class="chip-label">{{ type.name }}</p>
          </div>
        </div>
      </div>
    </v-card>
  </NuxtLink>
</template>

<script setup>
const { pokemon } = defineProps(['pokemon']);
// https://pokeapi.co/api/v2/pokemon/{id or name}/
// > name = name:"clefairy"
// > order = 56
// > types > [0].type.name
// > sprites > front_default / front_shiny / front_female

// height: 7
// weight": 69
// height
// abilities > [0].name
// [0].url > fetch info > effect_entries > [0].effect ( if language === 'en')
// evolutions https://pokeapi.co/api/v2/evolution-chain/{id}/ > evolves_to (array)
</script>

<style scoped lang="scss">
.card-link {
  text-decoration: none;
}
.card {
  display: flex;
  flex-direction: column;
  align-items: center;

  height: 100%;
  max-width: 100%;
  max-height: 250px;

  background-color: gainsboro;
  border-radius: 4px;
}
.card-img-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;

  width: 120px;
  height: 120px;

  padding: 10px;
}

.card-img {
  width: 100%;
  /* height: 100%; */
}

.card-data {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  width: 100%;
  padding: 10px;

  background-color: white;
}

.title {
  font-weight: 800;
}

.chips-wrapper {
  display: flex;
  grid-gap: 4px;
}

.chip {
  padding: 2px 4px;

  color: #333333;

  border: 1px solid #666666;
  border-radius: 4px;
}

.chip-label {
  margin-bottom: 0;

  font-size: 10px;
  line-height: 12px;
  text-transform: uppercase;
}
</style>
