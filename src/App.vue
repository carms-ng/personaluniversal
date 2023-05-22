<template>
  <Hero />
  <About />
  <Quote />
  <Crew />
</template>

<style scoped>
</style>

<script>
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Quote from './components/Quote.vue'
import Crew from './components/Crew.vue'

export default {
  components: {
    Hero,
    About,
    Quote,
    Crew,
  }
}
</script>
