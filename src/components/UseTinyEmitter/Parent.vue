<template>
  <div>
    <h1>Parent with Tiny Emitter</h1>
    <button @click="emitter.$emit('save')">Send Event</button>
    <slot />
  </div>
</template>
<script>
import { defineComponent } from 'vue'
import emitter from "../../eventBus";

export default defineComponent({
  setup() {
    return { emitter }
  },
  emits: [ 'save' ]
})
</script>
<style scoped>
div {
  background-color: #A7F3D0;
  padding: 1rem
}
</style>

