<script setup>
import { inject, onMounted, ref } from "vue";

// declare a ref to hold the element reference
// the name must match template ref value
const nav = ref(null);
const { setNavRef } = inject("navRef");
onMounted(() => {
  setNavRef(nav.value);
});
</script>

<template>
  <nav ref="nav">
    <slot></slot>
  </nav>
</template>
