<template>
  <section>
    <div className="card">
      <h2>{{ content.h2 }}</h2>
      <p v-for="pp in content.p" :key="pp">
        {{ pp }}
      </p>
    </div>
    <div id="members">
      <CrewMembers :members=content.members />
    </div>
  </section>
 </template>

<style scoped>
section {
  display: grid;
  place-items: center;
}
@media (min-width: 768px) {
  section {
    padding: 2rem;
  }
  .card {
    padding: 2rem;
    background: var(--off-white);
  }
  section > * {
    max-width: 960px;
  }
}

@media (min-width: 1240px) {
  section {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    gap: 2rem;
  }
  .card {
    grid-column: 2 / 6;
    grid-row: 2 / 11;
    align-self: center;
  }
  #members {
    grid-column: 6 / 12;
    grid-row: 2 / 11;
  }
}

</style>

<script>
import content from '../assets/content.json'
import Image from './Image.vue'
import CrewMembers from './CrewMembers.vue'

export default {
  data() {
    return {
      content: content.crew
    }
  },
  components: {
    Image,
    CrewMembers,
  }
}
</script>
