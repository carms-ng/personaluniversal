<template>
  <Hero />
  <About />
  <Quote />
  <Crew />
  <Info />
</template>

<style scoped>
</style>

<script>
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Quote from './components/Quote.vue'
import Crew from './components/Crew.vue'
import Info from './components/Info.vue'

export default {
  components: {
    Hero,
    About,
    Quote,
    Crew,
    Info,
  }
}
</script>
