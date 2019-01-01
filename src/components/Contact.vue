<template lang="pug">
.contact(:class="{ 'contact--completed': completed, 'contact--incompleted': !completed }")
  .contact__thanks
    .h2.text--center.contact__heading Thank you.
    .h3.text--center I'll be in touch shortly.
  
  .contact__ready
    .h2.text--center.contact__heading Get in touch
    .h3.text--center Let's grab some coffee ☕
    form.contact__form(@submit.prevent="submitForm()", :class="{ 'contact__form--processing': processing }")
      input(type="text" placeholder="Name" v-model="name" name="name" required)
      input(type="email" placeholder="Email" v-model="email" name="email" required)
      textarea(rows="4" placeholder="Message" v-model="message" name="message" required)
      .error(v-if="error") {{ error }}
      button.btn(type="submit") {{ processing ? 'Processing...' : 'Send' }}

</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      name: null,
      email: null,
      message: null,
      error: null,
      processing: false,
      completed: false
    };
  },
  methods: {
    submitForm() {
      this.error = null;
      this.processing = true;

      if (process.env.NODE_ENV === "development") {
        return setTimeout(() => {
          this.completed = true;
          this.processing = false;
        }, 2000);
      }

      axios
        .post("https://formspree.io/adam@raider.tech", {
          name: this.name,
          email: this.email,
          message: this.message
        })
        .then(res => {
          this.completed = true;
          this.processing = false;
        })
        .catch(res => {
          this.completed = false;
          this.processing = false;
          this.error = res.error;
        });
    }
  }
};
</script>

<style lang="sass" scoped>
.contact
  &--incompleted
    .contact__thanks
      display: none

  &--completed
    .contact__thanks
      opacity: 0
      height: 0
      animation-name: contactIn
      animation-duration: 0.5s
      animation-delay: 0.5s
      animation-fill-mode: forwards
      position: relative
      top: 10rem
    
    .contact__ready
      animation-name: contactOut
      animation-duration: 0.5s
      animation-fill-mode: forwards
      position: relative
      z-index: -1

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

@keyframes contactIn
  0%
    display: none
    height: auto
    opacity: 0

  1%
    display: block

  100%
    opacity: 1
    display: block
    

@keyframes contactOut
  0%
    display: block
    opacity: 1

  99%
    display: block
  
  100%
    opacity: 0
    display: none
</style>