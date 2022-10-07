<template>
  <form @submit="addToCart">
    <slot></slot>
  </form>
</template>
<script setup>
  import { isCartOpen, addCartItem } from "../cartStore";
  import { CartItemDisplayInfo } from "../cartStore";

  const cartInfo = CartItemDisplayInfo;

  const props = defineProps({
    item: CartItemDisplayInfo,
  });

  const addToCart = (e) => {
    e.preventDefault();
    isCartOpen.set(true);
    addCartItem(item);
  };
</script>
