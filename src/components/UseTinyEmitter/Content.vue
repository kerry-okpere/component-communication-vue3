<template>
  <div>
    <h1>Child with Tiny Emitter</h1>
    <small v-if="isEmitting">Capturing Parent event and emitting child.</small>
  </div>
</template>
<script>
import { defineComponent, ref, reactive } from 'vue'
import emitter from "../../eventBus";

export default defineComponent({
  setup(props, { emit }) {
    const isEmitting = ref(false)
    const state = reactive({
      data: {
        name: 'Victor',
        age: 2
      }
    })
    
    emitter.$on('save', () => {
      isEmitting.value = true
      console.log('handle data transfer with tiny emitter')
      emit('save', state.data)
      setTimeout(() => {
        isEmitting.value = false
        return state.data
      }, 2000);
    })

    return {
      isEmitting
    }
  },
  emits: [ 'save' ]
})
</script>
<style scoped>
div {
  background-color: #93C5FD;
  padding: 1rem;
  margin: 1rem 0;
}
</style>
