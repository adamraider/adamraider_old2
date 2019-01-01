<template lang="pug">
.skills
  .skills__heading.h2 Some of my favorite tools
  .skills__list
    .skill(v-for="skill in skills")
      img.skill__logo(:src="`/static/skills/${skill.image}`")
      .skill__name {{ skill.name }}
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          image: "js.svg",
          name: "JavaScript"
        },
        {
          image: "react.svg",
          name: "React"
        },
        {
          image: "vue.svg",
          name: "Vue.js"
        },
        {
          image: "jest.svg",
          name: "Jest"
        },
        {
          image: "rails.svg",
          name: "Ruby on Rails"
        },
        {
          image: "sass.svg",
          name: "Sass"
        },
        {
          image: "sketch.svg",
          name: "Sketch"
        },
        {
          image: "webpack.svg",
          name: "Webpack"
        },
        {
          image: "heroku.svg",
          name: "Heroku"
        }
      ]
    };
  }
};
</script>

<style lang="sass" scoped>
.skills
  max-width: 540px
  margin: 0 auto 10rem

  @media(min-width: 720px)
    max-width: 760px

  &__heading
    margin-bottom: 3rem
    text-align: center
  
  &__list
    display: flex
    flex-wrap: wrap
    justify-content: center

.skill
  margin: 0 1rem 3rem
  @media(min-width: 720px)
    margin: 0 2rem 3rem
  display: flex
  flex-direction: column
  align-items: center
  
  &__logo
    width: 4.5rem
    height: 4.5rem
    background-position: center
    background-size: contain
    background-repeat: no-repeat
    border-radius: 5px
    background: rgba(0,0,0,0.045)
    padding: 1rem

    @media(min-width: 720px)
      width: 6rem
      height: 6rem

  &__name
    margin-top: 1rem
    text-align: center
    opacity: 0.8
</style>