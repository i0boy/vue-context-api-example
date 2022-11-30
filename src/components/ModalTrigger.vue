<script setup lang="ts">
import { ButtonHTMLAttributes, defineProps, inject } from "vue";
interface Props extends ButtonHTMLAttributes {}
const { open, close, state } = inject("state");

defineProps<Props>();
const toggle = () => {
  if (state.value) {
    close();
  } else {
    open();
  }
};
</script>
<template>
  <button @click="toggle">
    <slot>{{ state ? "close" : "open" }} modal</slot>
  </button>
</template>
