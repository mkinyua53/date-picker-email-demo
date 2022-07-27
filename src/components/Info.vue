<template>
  <div class="app">
    <div class="content">
      <form @submit.prevent="sendEmail(form)">
        <mk-date-picker v-model="form.date" label="Pick a date" required></mk-date-picker>
        <mk-input v-model="form.email" type="email" label="Enter your email address" required></mk-input>
        <submit-button :loading="submitting"></submit-button>
        <div>{{ message }}</div>
      </form>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import MkDatePicker from './Mk/Inputs/DatePicker.vue'
import MkInput from './Mk/Inputs/TextInput.vue'
import SubmitButton from './Mk/Inputs/Button.vue'

export default defineComponent({
  name: 'InfoCollection',
  components: {
    MkDatePicker,
    MkInput,
    SubmitButton,
  },
  data () {
    return {
      form: {
        date: '',
        email: 'info@test.net',
      },
      message: '',
      submitting: false,
    }
  },
  methods: {
    sendEmail (form: {date: string, email: string}) {
      console.log(form)
      this.submitting = true
      setTimeout(() => {
        this.submitting = false
        this.message = 'Thank you for using our service!'
      }, 2000)
    },
  },
  watch: {
    message: function () {
      setTimeout(() => {
        this.message = ''
      }, 2500)
    },
  },
})
</script>

<style lang="scss" scoped>
  .app {
    min-height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
</style>
