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
#members {
  padding: 1rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5rem;
}
@media (min-width: 768px) {
  section {
    padding: 2rem;
    display: grid;
    justify-items: center;
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
    padding: 0 calc(100vw / 12);
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    align-items: center;
  }
  .card {
    padding: 3rem;
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
