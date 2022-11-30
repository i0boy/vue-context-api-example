<script setup>
import { KeepAlive, ref, shallowRef, watch } from "vue";

import ModalContext from "./components/ModalContext.vue";
import ModalLayout from "./components/ModalLayout.vue";
import ModalPortal from "./components/ModalPortal.vue";
import ModalTrigger from "./components/ModalTrigger.vue";
import ViteLogo from "./components/ViteLogo.vue";
const keyId = ref(1);
const current = shallowRef(ModalPortal);
const toggle = () => {
  keyId.value += 1;
};
watch(keyId, () => {
  console.log(keyId.value);
});
</script>

<template>
  <ModalContext>
    <div>
      <ModalLayout> 모달이 그려질 위치 !</ModalLayout>
      <ViteLogo></ViteLogo>
      <ModalTrigger></ModalTrigger>
    </div>
    <div :key="keyId">
      <KeepAlive>
        <component :is="current">
          모달머시기
          <div>
            <ModalTrigger> 모달 닫기 </ModalTrigger>
          </div>
        </component>
      </KeepAlive>
    </div>
    <button @click="toggle">캐시날리기!</button>
  </ModalContext>
</template>
