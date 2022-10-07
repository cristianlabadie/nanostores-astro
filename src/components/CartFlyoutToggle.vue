<template>
  <button
    class="border-none text-blue-600 border-2 border-blue-600 transition-all duration-150 bg-opacity-20 bg-transparent py-2 px-3 rounded-md text-sm font-bold cursor-pointer hover:bg-blue-300"
    @click="() => isCartOpen.set(!$isCartOpen)"
  >
    Cart
  </button>
</template>
<script setup>
  import { useStore } from "@nanostores/vue";
  import { isCartOpen } from "../cartStore";
  const $isCartOpen = useStore(isCartOpen);
</script>
