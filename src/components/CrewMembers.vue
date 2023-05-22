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
    border-radius: 50%;
    background: transparent;
    cursor: pointer;
    margin-right: 1rem;
    margin-bottom: 1rem;
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
      console.log('close')
    }
  },
  components: {
    MemberAvatar,
    MemberModal,
  }
}
</script>
