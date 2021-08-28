<template>
  <div>
    <h1>Parent</h1>
    <button @click="$emit('save')">Send Event</button>
    <slot />
  </div>
</template>
<script>
import { defineComponent } from 'vue'

export default defineComponent({
  setup() {},
  emits: [ 'save' ]
})
</script>
<style scoped>
div {
  background-color: #D1D5DB;
  padding: 1rem
}
</style>
