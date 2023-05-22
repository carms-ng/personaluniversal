<template>
  <section>
    <div className="card">
      <h2>{{ content.h2 }}</h2>
      <div>
        <div className="sub-section">
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24"><g fill="none"><path fill="currentColor" d="M4 7v2h16V7a2 2 0 0 0-2-2H6a2 2 0 0 0-2 2z"/><path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 5h2a2 2 0 0 1 2 2v2H4V7a2 2 0 0 1 2-2h2m8 0V3m0 2H8m0-2v2M4 9.5V19a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V9.5"/></g></svg>
          <div>
            <h6>{{ content.when.h6 }}</h6>
            <ul>
              <li v-for="li in content.when.li" :key="li">
                {{ li }}
              </li>
            </ul>
          </div>
        </div>

        <div className="sub-section">
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24"><path fill="currentColor" d="M12 11.5A2.5 2.5 0 0 1 9.5 9A2.5 2.5 0 0 1 12 6.5A2.5 2.5 0 0 1 14.5 9a2.5 2.5 0 0 1-2.5 2.5M12 2a7 7 0 0 0-7 7c0 5.25 7 13 7 13s7-7.75 7-13a7 7 0 0 0-7-7Z"/></svg>
          <div>
            <h6>{{ content.where.h6 }}</h6>
            <ul>
              <li v-for="li in content.where.li" :key="li">
                {{ li }}
              </li>
            </ul>
            <p v-for="p in content.where.p" :key="p">
              {{ p }}
            </p>
          </div>
        </div>

        <div className="sub-section">
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 16 16"><path fill="currentColor" d="M1.5 3A1.5 1.5 0 0 0 0 4.5V6a.5.5 0 0 0 .5.5a1.5 1.5 0 1 1 0 3a.5.5 0 0 0-.5.5v1.5A1.5 1.5 0 0 0 1.5 13h13a1.5 1.5 0 0 0 1.5-1.5V10a.5.5 0 0 0-.5-.5a1.5 1.5 0 0 1 0-3A.5.5 0 0 0 16 6V4.5A1.5 1.5 0 0 0 14.5 3h-13Z"/></svg>
          <div>
            <h6>{{ content.tix.h6 }}</h6>
            <div>
              <ul>
                <li>
                  <a :href=content.tix.website.href target="_blank">
                    {{ content.tix.website.text }}
                  </a>
                </li>
                <li>
                  <a :href=content.tix.phone.href>
                    {{ content.tix.phone.text }}
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.card > div {
  display: grid;
  gap: 2rem;
}
.sub-section {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 1rem;
}
p {
  margin-top: 1rem;
  margin-bottom: 0;
}

@media (min-width: 768px) {
  section {
    padding: 2rem;
    display: grid;
    place-content: center;
  }
  h6 {
    font-size: 1.5rem;
    margin: 0 0 1rem 0;
  }
  li {
    font-size: 1.25rem;
    line-height: 1.8;
  }
  .card {
    background: var(--off-white);
    max-width: 960px;
  }
}

@media (min-width: 1024px) {
  .card > div {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr;
  }
  .sub-section:nth-child(2) {
    grid-column: 2 / -1;
    grid-row: 1 / -1;
  }
}

@media (min-width: 1280px) {}



</style>

<script>
import content from '../assets/content.json'

export default {
  data() {
    return {
      content: content.info
    }
  },
}
</script>
