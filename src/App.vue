<template>
  <div>
    <info-collection></info-collection>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import InfoCollection from './components/Info.vue';

export default defineComponent({
  name: 'App',
  components: {
    InfoCollection,
  },
});
</script>

<style lang="scss">
#app {
  color: #2c3e50;
}
</style>
