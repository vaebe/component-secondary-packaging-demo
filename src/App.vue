<script setup lang="ts">
import { ref } from "vue";
import WrapInput from "./components/WrapInput.vue";

const inputText = ref('')

const prependSlotText =  ref('Http://')
const appendSlotText =  ref('.com')

function updateSlotInfo (){
  prependSlotText.value = 'https://'
  appendSlotText.value = `${new Date().getTime()}`
}

const wrapInputRef = ref()
function setWrapInputFocus () {
  wrapInputRef.value?.focus()
}
</script>

<template>
  <WrapInput v-model="inputText" ref="wrapInputRef">
    <template #prepend>{{ prependSlotText }}</template>
    <template #append>{{ appendSlotText }}</template>
  </WrapInput>

  <div style="margin: 20px 0;">
    {{inputText}}
  </div>

  <el-button type="primary" @click="updateSlotInfo">更新插槽内容</el-button>
  <el-button type="primary" @click="setWrapInputFocus">set input focus</el-button>
  
</template>

<style scoped>
</style>
