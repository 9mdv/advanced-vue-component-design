<template>
  <button
    type="button"
    class="text-red-dark hover:underline"
    @click="modalOpen = true"
  >
    Delete Account
    <portal to="modals" v-if="modalOpen">
      <confirm-delete-modal :show="modalOpen" @close="modalOpen = false" :account-id="accountId"/>
    </portal>
  </button>
</template>

<script>
import ConfirmDeleteModal from './ConfirmDeleteModal.vue'

export default {
  components: {
    ConfirmDeleteModal,
  },
  props: ['accountId'],
  data() {
    return {
      modalOpen: false,
    }
  },
}
</script>
