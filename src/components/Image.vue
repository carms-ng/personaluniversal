<template>
  <img :src="getImageUrl(filename)" :alt=alt />
</template>

<script>
export default {
  props: {
    filename: String,
    alt: String,
  },
  methods: {
    getImageUrl(filename) {
      return new URL(`../assets/${filename}`, import.meta.url).href
    }
  },
}
</script>
