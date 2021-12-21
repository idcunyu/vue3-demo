<template>
  <HelloWorld class="abcdefg" ref="son1" b="222" :cc="cc" @fn1="handleFn1">
    <template v-slot:taga>
      <div>slot slot a</div>
    </template>
    <template v-slot:tagb>
      <div>slot slot b</div>
    </template>
  </HelloWorld>
</template>

<script setup>
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
function handleFn1(aa, bb) {
  console.log('fn1', aa, bb)
}
const son1 = ref(null);
console.log(son1)

const cc = ref(666)
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
