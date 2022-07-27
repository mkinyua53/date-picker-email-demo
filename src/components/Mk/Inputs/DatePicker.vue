<template>
  <input-control>
    <label>
      <slot name="label">
        {{ label }}
        <input type="date" :value="modelValue" :label="label" @input="$emit('update:modelValue', $event.target.value)" :required="required">
      </slot>
    </label>
  </input-control>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import InputControl from './Input.vue'

export default defineComponent({
  name: 'DatePicker',
  props: {
    modelValue: String,
    label: {
      type: String,
    },
    required: {
      type: Boolean,
      default: false,
    },
  },
  emits: ['update:modelValue'],
  components: {
    InputControl,
  },
})
</script>
