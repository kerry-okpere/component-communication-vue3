<script setup>
import Parent from './Parent.vue'
import Content from './Content.vue'
import { ref } from 'vue'

const endEmit = data => {
  console.log('data has arrived through emitter', data)
}
</script>

<template>
  <Parent>
    <Content @save="endEmit"/>
  </Parent>
</template>

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
