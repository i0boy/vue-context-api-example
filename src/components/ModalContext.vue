<script setup>
import { provide, ref } from "vue";
import ModalOpenContext from "./ModalOpenContext.vue";

// declare a ref to hold the element reference
// the name must match template ref value
const navRef = ref(null);
const setNavRef = (el) => {
  navRef.value = el;
};
provide("navRef", { navRef, setNavRef });
</script>
<template>
  <ModalOpenContext>
    <slot></slot>
  </ModalOpenContext>
</template>
