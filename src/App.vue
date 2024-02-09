<script setup>
import { onBeforeMount } from 'vue'
import { useGamesStore } from '@/stores/games'
import { RouterView } from 'vue-router'
import Nav from '../src/components/Nav.vue'
import Footer from '../src/components/Footer.vue'

const store = useGamesStore();

onBeforeMount( () => {
   store.loadGames();
   console.log(store.getGames);  // Controleren
} );
</script>

<template>
   <Nav />

   <main>
      <div class="album py-5 bg-black">
      <RouterView />
      </div>
   </main>

   <Footer />
</template>

<style scoped>

</style>