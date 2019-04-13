<template>
  <div class="min-h-screen bg-grey-darker p-8">
    <div class="max-w-sm mx-auto">
      <user-settings-form></user-settings-form>
      <br>
      <div class="card">
        <label class="block">
          <span class="form-label mb-2">Select a date</span>
          <date-picker
            class="form-input"
            v-model="date"
            format="D MMM YYYY"
            :options="{ firstDay: 0 }"
          ></date-picker>
        </label>
      </div>
      <div class="min-h-screen flex items-center justify-center">
        <button @click="modalOpen = true" type="button" class="btn btn-blue">Open Modal</button>
      </div>
      <announcement-modal :show="modalOpen" @close="modalOpen = false"></announcement-modal>
    </div>
  </div>
</template>

<script>
import UserSettingsForm from './components/UserSettingsForm.vue'
import DatePicker from './components/DatePicker.vue'
import AnnouncementModal from './components/AnnouncementModal.vue'

export default {
  data() {
    return {
      date: null,
      modalOpen: false,
    }
  },
  components: {
    UserSettingsForm,
    DatePicker,
    AnnouncementModal,
  },
}
</script>

<style src="./assets/css/app.css"/>
