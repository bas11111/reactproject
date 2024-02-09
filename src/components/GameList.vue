<template>
  <GameCard v-for="game in store.getGames" :key="game.id" :game="game" />
</template> 

<script setup>
  import { useGamesStore } from '@/stores/games'    
  import GameCard from './Gamecard.vue'

  const store = useGamesStore();
</script>

<style scoped>

</style>