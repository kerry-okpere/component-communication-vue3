<script setup>
import Parent from './Parent.vue'
import Content from './Content.vue'
</script>

<template>
  <Parent @save="event = 'save'">
    <Content/>
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
