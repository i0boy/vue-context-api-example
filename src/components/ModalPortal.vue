<script setup>
import { inject } from "vue";
import ModalContent from "./ModalContent.vue";
const { open, close, state } = inject("state");
const { navRef } = inject("navRef");
</script>

<template>
  <template v-if="navRef">
    <Teleport :to="navRef">
      <div id="myModal" class="modal" v-if="state">
        <ModalContent>
          <slot></slot>
        </ModalContent>
      </div>
    </Teleport>
  </template>
</template>

<style scoped>
.modal {
  display: flex; /* Hidden by default */
  justify-content: center;
  align-items: center;
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}
</style>
