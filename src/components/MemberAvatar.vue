<template>
  <Image :filename=member.img.filename :alt="member.name"  />
</template>

<style scoped>
  img {
    width: 24vw;
    height: 24vw;
    max-width: 200px;
    max-height: 200px;
    border-radius: 50%;
    overflow: hidden;
    object-fit: cover;
    border: 3px solid var(--off-white);
  }
</style>

<script>
import Image from './Image.vue'

export default {
  props: {
    member: Object,
  },
  components: {
    Image,
  }
}
</script>
