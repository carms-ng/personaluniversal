<template>
  <section id="quote">
    <div className="card">
      <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 16 16"><path fill="currentColor" d="M7 7v7H0V6.9c0-4.8 4.5-5.4 4.5-5.4l.6 1.4s-2 .3-2.4 1.9C2.3 6 3.1 7 3.1 7H7zm9 0v7H9V6.9c0-4.8 4.5-5.4 4.5-5.4l.6 1.4s-2 .3-2.4 1.9c-.4 1.2.4 2.2.4 2.2H16z"/></svg>
      <p v-for="pp in content.quote.p" :key="pp">
        {{ pp }}
      </p>
      <h3>{{ content.quote.h3 }}</h3>
      <small>{{ content.quote.post }}</small>
      <Image :filename=content.quote.img.filename :alt=content.quote.img.alt />
    </div>
  </section>
 </template>

<style scoped>
svg {
  margin-bottom: 1rem;
}
p {
  font-style: italic;
}

h3 {
  margin: 2rem 0 0;
  text-align: center;
}
small {
  margin: 0.5rem 0;
  text-align: center;
}
small {
  display: block;
  font-size: 1rem;
}
img {
  display: block;
  width: 200px;
  margin: 0 auto;
  margin-top: 2rem;
}

@media (min-width: 768px) {
  section {
    display: grid;
    place-content: center;
    height: 100vh;
  }
  .card {
    background: var(--off-white);
    margin: 2rem;
  }
}

@media (min-width: 1024px) {
  .card {
    max-width: 960px;
    margin: 0 auto;
    position: relative;
  }
  h3 {
    margin: 5rem 0 0;
  }
  img {
    position: absolute;
    right: 3rem;
    bottom: 3rem;
  }
}

</style>

<script>
import content from '../assets/content.json'
import Image from './Image.vue'

export default {
  data() {
    return {
      content: content.about
    }
  },
  components: {
    Image,
  }
}
</script>
