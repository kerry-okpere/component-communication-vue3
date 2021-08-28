<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import Parent from './components/Parent.vue'
import Content from './components/Content.vue'
import UseTinyEmitter from './components/UseTinyEmitter/GrandParent.vue'

import { ref } from 'vue'

const event = ref('')
const endEmit = data => {
  // reset emit to default
  event.value = ''
  console.log('data has arrived', data)
  // ...
}
</script>

<template>
  <h1>Using Tiny Emitter</h1>
  <UseTinyEmitter />

  <h1>Using Props and Watchers</h1>
  <Parent @save="event = 'save'">
    <Content :event="event" @save="endEmit"/>
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
