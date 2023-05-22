<template>
  <dialog open={!!member}>
    <div className="modal-body">
      <button
        type="button"
        @click="closeModal"
      >
        <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 15 15"><path fill="currentColor" fill-rule="evenodd" d="M12.854 2.854a.5.5 0 0 0-.708-.708L7.5 6.793L2.854 2.146a.5.5 0 1 0-.708.708L6.793 7.5l-4.647 4.646a.5.5 0 0 0 .708.708L7.5 8.207l4.646 4.647a.5.5 0 0 0 .708-.708L8.207 7.5l4.647-4.646Z" clip-rule="evenodd"/></svg>
      </button>
      <MemberAvatar :member=member />
      <h2>{{ member.name }}</h2>
      <p v-for="p in member.bio" :key="p">
        {{ p }}
      </p>

    </div>
  </dialog>
</template>

<style scoped>
dialog {
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.8);
  margin: 0;
  padding: 0;
  border: 0;
}

.modal-body {
  width: 100%;
  height: 100%;
  overflow-y: auto;
  background-color: var(--off-brown);
  padding: 3rem 1rem;
  border: unset;
  z-index: 2;
  position: relative;
}
h2 {
  text-align: center;
}
img {
  margin: 0 auto;
  display: block;
}
button {
  position: fixed;
  top: 1rem;
  right: 1rem;
  background: unset;
  border: unset;
  cursor: pointer;
}

@media (min-width: 768px) {
  dialog {
    display: grid;
    place-items: center;
  }
  .modal-body {
    margin: 0;
    padding: 3rem;
    width: 720px;
    height: 720px;
  }
  button {
    top: calc((100vh - 720px) / 2 + 1.5rem);
    right: calc((100vw - 720px) / 2 + 1.5rem);
  }
}

</style>

<script>
import MemberAvatar from './MemberAvatar.vue'

export default {
  props: {
    member: Object,
    closeModal: {
      type: Function,
      default() {
        return {}
      }
    },
  },
  components: {
    MemberAvatar,
  },
}
</script>
