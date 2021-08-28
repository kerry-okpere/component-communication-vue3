<template>
  <div>
    <h1>Child</h1>
    <small v-if="isEmitting">Capturing Parent event and emitting child.</small>
  </div>
</template>
<script>
import { defineComponent, watch, ref, reactive } from 'vue'

export default defineComponent({
  props: {
    event: {
      type: String,
      validator(value) {
        return ['', 'save' ].includes(value)
      }
    }
  },
  setup(props, { emit }) {
    const isEmitting = ref(false)
    const state = reactive({
      data: {
        name: 'Victor',
        age: 2
      }
    })

    watch(() => props.event, (newValue) => {
      if(newValue == 'save') {
        emit('save', state.data)
        isEmitting.value = true
        console.log('Handle data transfer with props and watchers')
        setTimeout(() => {
          isEmitting.value = false
        }, 2000);
      }
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
