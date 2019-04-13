<template>
  <div class="card">
    <h1 class="text-2xl font-bold mb-6">Your Settings</h1>
    <label class="block mb-6">
      <span class="block text-grey-darker font-semibold mb-2">Email Address</span>
      <input v-model="email" class="form-input" placeholder="you@example.com">
    </label>
    <div class="mb-8">
      <span class="block text-grey-darker font-semibold mb-2">Newsletter</span>
      <div class="flex justify-between items-center">
        <p class="mr-4">Send you occasional news and updates.</p>
        <toggle-input v-model="receiveNewsletter" class="flex-no-shrink"/>
      </div>
    </div>
    <div class="flex justify-between">
      <delete-account-button :account-id="accountId"></delete-account-button>
      <button type="button" class="btn btn-blue" @click="submit">Update Settings</button>
    </div>
  </div>
</template>

<script>
import ToggleInput from './ToggleInput.vue'
import DeleteAccountButton from './DeleteAccountButton.vue'

export default {
  components: {
    ToggleInput,
    DeleteAccountButton,
  },
  props: ['accountId'],
  data() {
    return {
      email: 'jane@example.com',
      receiveNewsletter: false,
    }
  },
  methods: {
    submit() {
      console.log('Submitting preferences...', {
        email: this.email,
        receiveNewsletter: this.receiveNewsletter,
      })
    },
  },
}
</script>
