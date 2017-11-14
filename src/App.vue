<template lang="pug">
  #app.app
    .app__content
      .app__header
        .app__title
          h1.h1 Adam Raider is a web applications developer, designer and maker in New York City.
      
      Projects
      Skills
      Companies
      Contact
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
</style>
