<script setup>
import { provide, ref } from "vue";

// declare a ref to hold the element reference
// the name must match template ref value
const navRef = ref(null);
const setNavRef = (el) => {
  navRef.value = el;
};
provide("navRef", { navRef, setNavRef });
</script>
<template>
  <slot></slot>
</template>
