<script setup lang="ts">
import { h, ref } from "vue";
import { ElInput } from "element-plus";
const model = defineModel()

const inputRef = ref()

defineExpose(new Proxy({}, {
  get(_target, prop)  {
    console.log('来自父组件的调用:', prop)
    return inputRef.value?.[prop]
  },
  has (_target, prop) {
    return prop in inputRef.value
  }
}))

</script>

<template>
  <component :is="h(ElInput, $attrs, $slots)" v-model="model" ref="inputRef"></component>
</template>

<style lang='scss' scoped></style>