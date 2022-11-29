<script setup>
import { inject } from "vue";

const { navRef } = inject("navRef");
</script>

<template>
  <template v-if="navRef">
    <Teleport :to="navRef">
      <div>
        <h1>모달</h1>
        <p>모달 내용</p>
      </div>
    </Teleport>
  </template>
</template>
