<template lang="pug">
  #app.app
    .app__content
      .app__header
        .app__title
          h1.h1 Adam Raider is a web applications developer, designer and maker in New York City.
          .app__icon
        //- .app__actions
        //-   button.btn Message Adam
        //-   button.btn.btn--secondary Don't message Adam
      
      Projects
      Skills
      Companies
      Contact

      .app__footer
        span made by adam in nyc.
</template>

<script>
import Companies from './components/Companies'
import Contact from './components/Contact'
import Projects from './components/Projects'
import Skills from './components/Skills'

export default {
  name: 'app',
  components: {
    Companies, Contact, Projects, Skills
  },
  data () {
    return {
      error: null
    }
  }
}
</script>

<style lang="sass">
@import './sass/base'

.app
  &__content
    max-width: 1080px
    margin: 6rem auto
    @media(min-width: 720px)
      margin: 8rem auto
    padding: 0 1rem
    font-size: 1rem
    color: #333

  &__header
    margin-bottom: 5rem
    
  &__title
    display: flex

  &__footer
    text-align: center
    margin-top: 6rem
    opacity: 0.35

  &__icon
    margin-left: auto
    width: 1.25em
    height: 1.25em
    border: 3px solid #000
    border-radius: 1em
    position: relative
    display: none
    @media(min-width: 720px)
      display: block
</style>
