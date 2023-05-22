<template>
  <section>
    <div className="card">
      <h2>{{ content.h2 }}</h2>
      <p v-for="pp in content.p" :key="pp">
        {{ pp }}
      </p>
    </div>
    <Image :filename=content.img.filename :alt=content.img.alt />
  </section>
</template>

<style scoped>
p {
  margin-bottom: 2rem;
}
img {
  max-width: 100%;
}

@media (min-width: 768px) {
  .card {
    background: var(--off-white);
    margin: 2rem;
  }
}

@media (min-width: 1024px) {
  section {
    display: grid;
    height: 100vh;
    width: 100vw;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: repeat(12, 1fr);
  }
  section > div {
    grid-column: 2 / 10;
    grid-row: 2 / 11;

    z-index: 1;
    align-self: center;
  }
  section > img {
    grid-column: 6 / -1;
    grid-row: 1 / 12;

    object-fit: cover;
    height: 100vh;
  }
}

@media (min-width: 1280px) {
  section > div {
    grid-column: 2 / 8;
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
