<template>
  <div id="app">
    <div ref="countref">{{ count }}</div>
    <img alt="Vue logo" src="./assets/logo.png" @click="click" />
    <HelloWorld msg="Welcome to Your Vue.js App" :obj="obj" />
    <he-dhe v-bind="obj" v-model="count" />{{ count }}
    <h2>hahaha</h2>
    113
  </div>
</template>

<script setup>
import { ref, nextTick } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import HeDhe from "./components/hehe.vue";

const count = ref(0);
const countref = ref(null);
const obj = ref({
  a: 1,
  b: 2,
  c: 3,
});

const click = () => {
  for (let i = 0; i < 10; i++) {
    // nextTick(() => {
    //   console.log(count.value);
    //   console.log(countref.value.innerHTML);
    // })
  }
  count.value = 10;
  console.log(countref.value.innerText);
  nextTick(() => {
    console.log(countref.value.innerHTML);
  });
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
