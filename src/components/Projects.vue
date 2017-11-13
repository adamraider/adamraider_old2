<template lang="pug">
.projects
  .project
    .project__browser
      img(src="/static/examples/extensions.png")

    .project__info
      .h2.project__heading Extensions.af
      .project__subheading Maker
      .project__desc #[strong #1 on Product Hunt]. The best chrome extensions on the internet. Extensions is a single page application built with Vue.js paired with a Rails + Postgres backend.

  .project
    .project__browser
      img(src="/static/examples/swipebuy.png")

    .project__info
      .h2.project__heading Swipebuy
      .project__subheading Maker
      .project__desc #[strong #4 on Product Hunt]. Sell from Instagram and Snapchat like a piece of cake. Customizable Vue.js application with animations and UI imitating a messaging app. Integrates with Stripe for payments.

  .project
    .project__browser
      img(src="/static/examples/mealpal.png")

    .project__info
      .h2.project__heading MealPal
      .project__subheading Software Engineer
      .project__desc Serving up lunch and dinner for #[strong thousands of users]. Built out full-stack functionality for new features. Such as, modualar signup experiences, internationalization, new visual designs and more.
</template>

<script>
export default {
}
</script>

<style lang="sass" scoped>
.projects
  margin-bottom: 10rem

.project
  display: flex
  width: 100%
  &:not(:last-child)
    margin-bottom: 6rem
  
  &__browser
    width: 100%
    max-width: 800px
    margin-right: 4rem
    position: relative
    img
      box-shadow: 0 12px 80px rgba(102, 125, 178, 0.2)

  &__info
    padding-top: 3rem
    width: 54%

  &__heading
    margin-bottom: 0.5rem

  &__subheading
    font-size: 1.25rem
    margin-bottom: 1rem
    opacity: 0.5

  &__desc
    color: #757575
    font-size: 1.25em
    line-height: 1.9
    &:not(:last-child)
      margin-bottom: 1em
    
    strong
      font-weight: 500
      color: #424242
</style>