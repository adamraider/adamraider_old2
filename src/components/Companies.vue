<template lang="pug">
.companies
  .companies__heading.h2.text--center Companies I've worked with.
  .companies__images
    .companies__example(v-for="brand in companies", :class="`companies__example--${brand.class}`"): img(:src="`${brand.image}`", :alt="brand.name")
</template>

<script>
export default {
  data () {
    return {
      companies: [
        {
          image: '/static/privacy.svg',
          name: 'Privacy',
          class: 'privacy'
        },
        {
          image: '/static/tokenly2.png',
          name: 'Tokenly',
          class: 'tokenly'
        },
        {
          image: '/static/mealpal.svg',
          name: 'MealPal',
          class: 'mealpal'
        },
        {
          image: '/static/nycda.svg',
          name: 'New York Code + Design Academy',
          class: 'nycda'
        },
        {
          image: '/static/getaway.svg',
          name: 'Getaway',
          class: 'getaway'
        }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
.companies
  max-width: 960px
  margin: 0 auto 10rem

  &__heading
    margin-bottom: 3.5rem

  &__images
    display: flex
    flex-wrap: wrap
    justify-content: center

  &__example
    width: 12rem
    margin: 0 3rem 3rem
    background-size: contain
    background-repeat: no-repeat
    background-position: center
    position: relative
    display: flex
    align-items: center

    &--getaway
      top: 6px

    &--nycda
      top: 1px
</style>