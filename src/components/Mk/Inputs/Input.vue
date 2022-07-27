<template>
  <div class="mk-form-control">
    <slot name="default"></slot>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MkInputControl',
})
</script>

<style lang="scss" scoped>
  .mk-form-control {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    padding: 10px;
  }
</style>

<style lang="scss">
  input {
    width: 100%;
    padding: 2px;
    border-radius: 5px;
  }
</style>
