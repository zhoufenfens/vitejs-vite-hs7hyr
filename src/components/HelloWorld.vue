
<template>
  <h1>{{ msg }}</h1>

  <div class="card cccccddddddww">
    <button type="button" @click="add">count is {{ count }}</button>
    <div>
      <ul>
        <li v-for="(item, index) in arr" :key="index">
          {{item.item}}
        </li>
      </ul>
    </div>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>


<script setup>
import { ref, onMounted, reactive, } from 'vue'

defineProps({
  msg: String
});

let count = ref(0);

let arr = reactive([]);

const add = ()=> {
  console.log('add', count);
  count.value++;
  arr.push({
    item: count.value,
  });
};



console.log(this, 123);

onMounted(()=> {
  console.log('mounted211', this);
});



</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
