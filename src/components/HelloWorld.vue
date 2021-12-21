<template>
  <div class="hello">
    <slot name="tagb"></slot>
    <div ref="oneRef" id="oneRef" @click="handleClickOneRef($event), handleClickOneRefAfter()">oneRef</div>
    <div @click="handleClickFn1">fn1</div>
    <slot name="taga"></slot>
  </div>
</template>

<script setup>
import { ref, defineProps, defineEmits, defineExpose, useSlots, useAttrs, getCurrentInstance } from 'vue';

const vm = getCurrentInstance();
console.log("vm", vm)

const props = defineProps({
  a: {
    type: String,
  },
  b: String,
})

console.log('props', props)
const emit = defineEmits(['fn1'])

const aa = 1
const bb = ref(2)

defineExpose({
  aa,
  bb,
})

function handleClickOneRef(e) {
  console.log('handleClickOneRef', e)
}

function handleClickOneRefAfter() {
  console.log("handleClickOneRefAfter")
}

function handleClickFn1() {
  emit('fn1', '111', '222')
}

const oneRef = ref(null);
handleClickOneRef()

const slots = useSlots()
const attrs = useAttrs()

console.log(slots, attrs)

</script>

<style scoped>

</style>
