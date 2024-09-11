<script setup lang="ts">
import { ref } from "vue";
import WrapInput from "./components/WrapInput.vue";

const inputText = ref('')
</script>

<template>
  <WrapInput v-model="inputText"></WrapInput>

  <div>
    {{inputText}}
  </div>
</template>

<style scoped>
</style>
