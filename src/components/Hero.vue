<template>
  <section>
    <img :src=content.img.filepath :alt=content.img.alt />
    <div className="card-hero">
      <small>{{ content.pre }}</small>
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
h1 {
  font-size: 2.25rem;
  line-height: 1;
  margin: 0;
  color: var(--purple);
  font-style: italic;
}
small {
  font-weight: 700;
  color: var(--purple);
}
img {
  width: 100%;
  object-fit: cover;
  height: 60vh;
}

.card-hero {
  padding: 1rem;
  text-align: left;
  display: grid;
  place-content: space-evenly;
  gap: 0.5rem;
  height: 40vh;
}

.btn-primary {
  display: block;
  width: 100%;
  height: 3rem;
  color: #fff;
  background-color: var(--brown);
  text-align: center;
  border-radius: 1rem;
  display: grid;
  place-content: center;
}
.btn-primary:hover {
  opacity: 0.95;
}


@media (min-width: 768px) {
  small {
    font-size: 1.5rem;
  }
  h1 {
    font-size: 3rem;
  }
  p {
    font-size: 1.5rem;
  }
  .btn-primary {
    font-size: 1.5rem;
    height: 4rem;
  }
  .card-hero {
    padding: 2rem;
  }
}

@media (min-width: 1024px) {
  section {
    display: grid;
    height: 100vh;
  }
  section > img {
    grid-column: 1 / 12;
    grid-row: 1 / 12;
  }
  section > div {
    grid-column-end: 11;
    grid-row-end: 11;
  }
  img {
    height: 100vh;
    object-position: 20% 80%;
  }
  h1 {
    font-size: 3.5rem;
  }

  .card-hero {
    background: var(--off-white);
    max-width: 640px;
    height: unset;
    max-height: 640px;
    padding: 3rem;
    gap: 1.5rem;
  }
}


</style>

<script>
import content from '../assets/content.json'

export default {
  data() {
    return {
      content: content.hero
    }
  }
}
</script>
