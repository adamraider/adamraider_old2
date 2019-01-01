<template lang="pug">
.companies
  .companies__heading.h2.text--center Companies I've worked with
  .companies__images
    .companies__example(v-for="brand in companies", :class="`companies__example--${brand.class}`"): img(:src="`${brand.image}`", :alt="brand.name")
</template>

<script>
export default {
  data() {
    return {
      companies: [
        {
          image: "/static/companies/wework.svg",
          name: "WeWork",
          class: "wework"
        },
        {
          image: "/static/companies/privacy.png",
          name: "Privacy",
          class: "privacy"
        },
        {
          image: "/static/companies/tokenly3.png",
          name: "Tokenly",
          class: "tokenly"
        },
        {
          image: "/static/companies/mealpal.svg",
          name: "MealPal",
          class: "mealpal"
        },
        {
          image: "/static/companies/nycda.svg",
          name: "New York Code + Design Academy",
          class: "nycda"
        },
        {
          image: "/static/companies/getaway.svg",
          name: "Getaway",
          class: "getaway"
        }
      ]
    };
  }
};
</script>

<style lang="sass" scoped>
.companies
  max-width: 530px
  margin: 0 auto 10rem

  @media(min-width: 720px)
    max-width: 760px

  
  &__heading
    margin-bottom: 3.5rem

  &__images
    display: flex
    flex-wrap: wrap
    justify-content: center

  &__example
    width: 7rem
    margin: 0 1rem 3rem
    @media(min-width: 720px)
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