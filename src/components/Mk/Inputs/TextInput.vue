<template>
  <input-control>
    <label>
      <slot name="label">
        {{ label }}
      </slot>
      <input :type="type" :minLength="minLength" :maxLength="maxLength" :placeholder="placeholder" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" :required="required">
    </label>
  </input-control>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import InputControl from './Input.vue'

export default defineComponent({
  name: 'TextInput',
  props: {
    modelValue: String,
    type: {
      type: String,
      default: 'text',
    },
    minLength: {
      type: Number || String,
    },
    maxLength: {
      type: Number || String,
    },
    placeholder: {
      type: String,
    },
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
