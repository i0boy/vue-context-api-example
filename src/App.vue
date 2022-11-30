<script setup>
import { ref } from "vue";
import ModalContext from "./components/ModalContext.vue";
import ModalLayout from "./components/ModalLayout.vue";
import ModalPortal from "./components/ModalPortal.vue";
import ModalTrigger from "./components/ModalTrigger.vue";
import ViteLogo from "./components/ViteLogo.vue";
const open = ref(false);

const toggle = () => {
  open.value = !open.value;
};
</script>

<template>
  <ModalContext>
    <div>
      <ModalLayout> 모달이 그려질 위치 </ModalLayout>
      <ViteLogo></ViteLogo>
      <ModalTrigger></ModalTrigger>
    </div>
    <ModalPortal>
      모달머시기
      <div>
        <ModalTrigger> 모달 닫기 </ModalTrigger>
      </div>
    </ModalPortal>
  </ModalContext>
</template>
