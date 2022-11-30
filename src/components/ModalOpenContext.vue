<script setup>
import { provide, ref } from "vue";

// declare a ref to hold the element reference
// the name must match template ref value
const state = ref(false);
const open = (el) => {
  state.value = true;
};
const close = (el) => {
  state.value = false;
};
provide("state", { open, close, state });
</script>
<template>
  <slot></slot>
</template>
