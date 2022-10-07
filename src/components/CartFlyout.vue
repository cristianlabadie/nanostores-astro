<template>
  <aside
    v-if="!$isCartOpen"
    class="fixed right-0 top-10 h-screen bg-slate-200 px-2 min-w-[300px] border-l-slate-400"
  >
    <ul
      class="list-none p-0"
      role="list"
      v-if="Object.values($cartItems).length"
    >
      <li
        class="flex gap-4 items-center"
        v-for="(cartItem, idx) in cartItems"
        :key="idx"
      >
        <img class="w-16" :src="cartItem.imageSrc" :alt="cartItem.name" />
        <div>
          <h3>{cartItem.name}</h3>
          <p>Quantity: {cartItem.quantity}</p>
        </div>
      </li>
    </ul>

    <p v-else>Your cart is empty!</p>
  </aside>
</template>
<script setup>
  import { useStore } from "@nanostores/vue";
  import { cartItems, isCartOpen } from "../cartStore";

  const $isCartOpen = useStore(isCartOpen);
  const $cartItems = useStore(cartItems);
</script>
