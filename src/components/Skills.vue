<template lang="pug">
.skills
  .skills__heading.h2 Some of my favorite tools.
  .skills__list
    .skill(v-for="skill in skills")
      img.skill__logo(:src="`/static/skills/${skill.image}`")
      .skill__name {{ skill.name }}
</template>

<script>
export default {
  data () {
    return {
      skills: [
        {
          image: 'js.svg',
          name: 'JavaScript ES6'
        },
        {
          image: 'vue.svg',
          name: 'Vue.js'
        },
        {
          image: 'rails.svg',
          name: 'Ruby on Rails'
        },
        {
          image: 'sass.svg',
          name: 'Sass'
        },
        {
          image: 'sketch.svg',
          name: 'Sketch'
        },
        {
          image: 'webpack.svg',
          name: 'Webpack'
        },
        {
          image: 'heroku.svg',
          name: 'Heroku'
        },
        {
          image: 'sublime.svg',
          name: 'Sublime Text'
        }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
.skills
  max-width: 800px
  margin: 0 auto 10rem
  
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
    width: 3rem
    height: 3rem
    @media(min-width: 720px)
      width: 5rem
      height: 5rem
    background-position: center
    background-size: contain
    background-repeat: no-repeat

  &__name
    margin-top: 2rem
    text-align: center
    opacity: 0.5
    font-weight: 500
</style>