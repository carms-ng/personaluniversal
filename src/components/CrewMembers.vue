<template>
  <button
    v-for="member in members"
    :key="member.name"
    type="button"
    @click="setActiveMember(member)"
  >
    <MemberAvatar :member=member />
  </button>
  <MemberModal
    v-if=!!activeMember
    :member=activeMember
    :closeModal="closeModal"
  />
</template>

<style scoped>
  button {
    border: unset;
    background: transparent;
    cursor: pointer;
    border-radius: 50%;
  }
</style>

<script>
import MemberAvatar from './MemberAvatar.vue'
import MemberModal from './MemberModal.vue'

export default {
  props: {
    members: Array,
  },
  data() {
    return {
      activeMember: null
    }
  },
  methods: {
    setActiveMember(member) {
      this.activeMember = member
    },
    closeModal() {
      this.activeMember = null
    },
    closeModalOnEscapeKeydown(e) {
      if (e.key === 'Escape') this.activeMember = null
    },
  },
  components: {
    MemberAvatar,
    MemberModal,
  },
  watch: {
    activeMember(newMember, _oldMember) {
      if (!!newMember) {
        window.addEventListener('keydown', this.closeModalOnEscapeKeydown)
      } else {
        window.removeEventListener('keydown', this.closeModalOnEscapeKeydown)
      }
    }
  }
}
</script>
