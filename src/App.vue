<script setup>
import { ref } from "vue";
import ModalContext from "./components/ModalContext.vue";
import ModalLayout from "./components/ModalLayout.vue";
import ModalPortal from "./components/ModalPortal.vue";
const open = ref(false);

const toggle = () => {
  open.value = !open.value;
};
</script>

<template>
  <ModalContext>
    <ModalLayout> 모달이 그려질 위치 </ModalLayout>
    <div>
      <a href="https://vitejs.dev" target="_blank">
        <img src="/vite.svg" class="logo" alt="Vite logo" />
      </a>
    </div>
    <button @click="toggle">{{ open ? "open" : "close" }} modal</button>
    <ModalPortal v-if="open" />
  </ModalContext>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
