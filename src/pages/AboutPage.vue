<template>
  <q-page padding class="flex flex-center">
  <button style="position: absolute; right: 15px">
    tag
  </button>

  <input v-model="message"
         @keyup.esc="clearInput"
         @keyup.enter="submit"
         @mouseenter="inputCheckIn"
         @mouseleave="inputCheckOut" />
  <button @click="submit">Submit</button>
  <h5 class="border-login"
      v-show="!message.length">
    Input Required
  </h5>
</q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      message: 'Input'
    }
  },
  computed: {
    //Throw computed values in here
  },
  methods: {
    submit() {
      this.message = 'Submitted';
      alert(this.message)
    },
    clearInput() {
      this.message = ''
    },
    inputCheckOut() {
      if (this.message == '') {
        this.message = 'Input'
      }
    },
    inputCheckIn() {
      if (this.message == 'Input') {
        this.message = ''
      }
    },
  }
})
</script>

<style>
  .border-login{
    border: 1px solid grey
  }
</style>
