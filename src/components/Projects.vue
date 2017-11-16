<template lang="pug">
.projects
  .project
    .project__browser
      img(src="/static/examples/framed_extensions.png")

    .project__info
      .h2.project__heading Extensions.af
      .project__subheading Maker
      .project__desc #[strong #1 on Product Hunt]. The best chrome extensions on the Internet. Extensions is a single page application built with Vue.js paired with a Rails + Postgres backend.

  .project
    .project__browser
      img(src="/static/examples/framed_swipebuy.png")

    .project__info
      .h2.project__heading Swipebuy
      .project__subheading Maker
      .project__desc #[strong #4 on Product Hunt]. Sell from Instagram and Snapchat like a piece of cake. Customizable Vue.js application with animations and UI imitating a messaging app. Integrates with Stripe for payments.

  .project
    .project__browser
      img(src="/static/examples/framed_mealpal.png")

    .project__info
      .h2.project__heading MealPal
      .project__subheading Software Engineer
      .project__desc Serving up lunch and dinner for #[strong thousands of users]. Built out full-stack functionality for new features. Such as, modular signup experiences, internationalization, new visual designs and more.
</template>

<script>
export default {
}
</script>

<style lang="sass" scoped>
$grid-gutter-width: 4rem
.projects
  margin-bottom: 10rem
    
.project
  display: flex
  width: 100%
  flex-direction: column
  justify-content: space-between
  @media(min-width: 720px)
    flex-direction: row
  &:not(:last-child)
    margin-bottom: 6rem
  
  &__browser
    position: relative
    width: calc(#{percentage(1/1.618)} - #{$grid-gutter-width / 2})
    img
      filter: drop-shadow(0 12px 80px rgba(102, 125, 178, 0.2))

  &__info
    padding-top: 3.5rem
    @media(min-width: 720px)
      width: calc(#{percentage(1-1/1.618)} - #{$grid-gutter-width / 2}) 

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