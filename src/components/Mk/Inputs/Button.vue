<template>
  <input-control>
    <input :type="type" :value="loading ? 'Submitting' : value" :style="{ cursor: cursor }">
  </input-control>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import InputControl from './Input.vue'

export default defineComponent({
  name: 'TextInput',
  props: {
    type: {
      type: String,
      default: 'submit',
    },
    color: {
      type: String,
      default: 'blue',
    },
    loading: {
      type: Boolean,
      default: false,
    },
    value: {
      type: String,
      default: 'Submit',
    },
  },
  components: {
    InputControl,
  },
  computed: {
    cursor() {
      return this.loading ? 'progress' : 'pointer'
    },
  },
})
</script>

<style lang="scss" scoped>
  input {
    width: fit-content;
    padding: 3px 7px;
  }
  input:hover {
    box-shadow: 2px 2px 10px 1px rgba(0, 0, 0, 0.2);
  }
</style>
