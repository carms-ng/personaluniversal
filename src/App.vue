<template>
  <Hero />
  <About />
  <Quote />
</template>

<style scoped>
</style>

<script>
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Quote from './components/Quote.vue'

export default {
  components: {
    Hero,
    About,
    Quote,
  }
}
</script>
