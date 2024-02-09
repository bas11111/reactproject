<template>
   <div class="col">
      <div class="card shadow-sm">
         <img :src="props.game.image" alt="" class="game-image" />
         <div class="card-body py-5 bg-black">
               <p class="card-text text-white">
                  {{ props.game.description }}
               </p>
               <div class="d-flex justify-content-between align-items-center">
                  <div class="btn-group">
                     <button type="button" class="btn btn-sm btn-outline-secondary">
                           <i class="las la-info-circle icon-size"></i>&nbsp;Info
                     </button>
                     <button type="button" class="btn btn-sm btn-danger" @click="addToCart(props.game.id)">
                           <i class="las la-cart-plus icon-size text-white"></i>&nbsp;Buy
                     </button>
                  </div>
                  <small class="fs-3 fw-bold text-info">&euro; {{ props.game.price }}</small>
               </div>
         </div>
      </div>
   </div>
</template>

<script setup>
import { useGamesStore } from '@/stores/games';

const props = defineProps({
   game: Object
});
const store = useGamesStore();

function addToCart(id)
{
   console.log(id);
   store.addToCart(id);
}

</script>

<style scoped>

</style>



