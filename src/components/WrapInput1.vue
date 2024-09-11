<script setup lang="ts">
import { h, ref} from "vue";
import { ElInput } from "element-plus";
const model = defineModel()

const inputRef = ref()

function getRef () {
  return inputRef.value
}

defineExpose({
  getRef
})
</script>

<template>
  <component ref="inputRef" :is="h(ElInput, $attrs, $slots)" v-model="model"></component>
</template>

<style lang='scss' scoped></style>