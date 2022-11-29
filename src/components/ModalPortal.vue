<script setup>
import { inject } from "vue";

// declare a ref to hold the element reference
// the name must match template ref value
const { getNavRef } = inject("navRef");
const navRef = getNavRef();
</script>

<template>
  <Teleport :to="navRef">
    <div>
      <h1>모달</h1>
      <p>모달 내용</p>
    </div>
  </Teleport>
</template>
