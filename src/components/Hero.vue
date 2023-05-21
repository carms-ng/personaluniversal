<template>
  <section>
    <div className="img-wrapper">
      <Image :filename=content.img.filename :alt=content.img.alt />
      <AnimatedLogo />
    </div>
    <div className="card card-hero">
      <small>{{ content.small }}</small>
      <h1>{{ content.h1 }}</h1>
      <p v-for="pp in content.p" :key="pp">
        {{ pp }}
      </p>
      <a
        className="btn-primary"
        :href=content.link.url
        target="_blank"
      >
        {{ content.link.text }}
      </a>
    </div>
  </section>
</template>

<style scoped>
small {
  font-weight: 700;
  color: var(--purple);
}
section {
  display: grid;
  height: 100vh;
  grid-template-rows: 1fr auto;
}
.img-wrapper {
  overflow: hidden;
}
.img-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-hero {
  text-align: left;
  display: grid;
  margin: 0;
  margin-bottom: 1rem;
  gap: 1rem;
}

.btn-primary {
  display: block;
  width: 100%;
  height: 3rem;
  color: #fff;
  background-color: var(--brown);
  text-align: center;
  border-radius: var(--br);
  display: grid;
  place-content: center;
}
.btn-primary:hover {
  opacity: 0.95;
}

@media (min-width: 768px) {
  small {
    font-size: 1.25rem;
  }
  .btn-primary {
    font-size: 1.5rem;
    height: 4rem;
  }
}

@media (min-width: 1024px) {
  section {
    grid-template-rows: unset;
  }
  section > .img-wrapper {
    grid-column: 1 / 12;
    grid-row: 1 / 12;
  }
  section > .card-hero {
    grid-column-end: 11;
    grid-row-end: 11;
  }

  .img-wrapper > img {
    height: 100vh;
    object-position: 20% 80%;
  }

  .card-hero {
    background: var(--off-white);
    max-width: 640px;
    height: unset;
    max-height: 640px;
    gap: 1.5rem;
  }
}

</style>

<script>
import content from '../assets/content.json'
import AnimatedLogo from './AnimatedLogo.vue'
import Image from './Image.vue'

export default {
  data() {
    return {
      content: content.hero
    }
  },
  methods: {
    getImageUrl(filename) {
      return new URL(`../assets/${filename}`, import.meta.url).href
    }
  },
  components: {
    AnimatedLogo,
    Image,
  }
}
</script>
