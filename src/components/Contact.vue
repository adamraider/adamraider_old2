<template lang="pug">
.contact
  template(v-if="completed")
    .h2.text--center.contact__heading Thank you.
    .h3.text--center I'll be in touch shortly.
  
  template(v-else)
    .h2.text--center.contact__heading I'd love to work with you.
    .h3.text--center How do you take your coffee?
    form.contact__form(@submit.prevent="submitForm()", :class="{ 'contact__form--processing': processing }")
      input(type="text" placeholder="Name" v-model="name" name="name" required)
      input(type="email" placeholder="Email" v-model="email" name="email" required)
      textarea(rows="4" placeholder="Message" v-model="message" name="message" required)
      .error(v-if="error") {{ error }}
      button.btn(type="submit") {{ processing ? 'Processing...' : 'Send' }}

</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      name: null,
      email: null,
      message: null,
      error: null,
      processing: false,
      completed: false
    }
  },
  methods: {
    submitForm () {
      this.error = null
      this.processing = true
      axios.post('https://formspree.io/adamjraider@gmail.com', {
        name: this.name,
        email: this.email,
        message: this.message
      }).then(res => {
        this.completed = true
        this.processing = false
        console.log(res)
      }).catch(res => {
        this.completed = false
        this.processing = false
        this.error = res.error
      })
    }
  }
}
</script>

<style lang="sass" scoped>
.contact
  &__heading
    margin-bottom: 0.75rem

  &__form
    display: flex
    flex-direction: column
    max-width: 24rem
    margin: 0 auto

    &--processing
      input, textarea, button
        pointer-events: none

      .btn
        background: #333

    input, textarea
      border: 0
      outline: 0
      font-size: 1.25rem
      padding: 0.75rem 1.2rem
      background-color: #f5f5f5
      margin-bottom: 0.75rem
      border-radius: 0.5rem
      transition: 0.15s ease
</style>