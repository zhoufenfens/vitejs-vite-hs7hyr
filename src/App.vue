<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue'
import { ref, onMounted, reactive, defineExpose, watchEffect, watch } from 'vue'

const helloWorld = ref(null);

watchEffect(()=> {
  if (helloWorld.value) {
    console.log(helloWorld.value.arr, 11);
  }
});

watch(helloWorld, ()=> {
  console.log(helloWorld.value.count);
}, {
  flush: 'post',
});

onMounted(()=> {
  console.log('mounted', helloWorld.value.arr);
});


</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue"  ref="helloWorld"/>
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
