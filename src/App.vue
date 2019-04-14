<template>
  <div class="min-h-screen p-8">
    <div class="max-w-sm mx-auto mb-8">
      <user-settings-form :account-id="accountId"></user-settings-form>

      <div class="card mt-8">
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
    </div>

    <div class="max-w-sm mx-auto">
      <p
        class="mb-6"
      >It was the best of times, it was the worst of times, it was the age of wisdom, it was the age of foolishness, it was the epoch of belief, it was the epoch of incredulity, it was the season of Light, it was the season of Darkness, it was the spring of hope, it was the winter of despair, we had everything before us, we had nothing before us, we were all going direct to Heaven, we were all going direct the other way--in short, the period was so far like the present period, that some of its noisiest authorities insisted on its being received, for good or for evil, in the superlative degree of comparison only.</p>
      <p
        class="mb-6"
      >There were a king with a large jaw and a queen with a plain face, on the throne of England; there were a king with a large jaw and a queen with a fair face, on the throne of France. In both countries it was clearer than crystal to the lords of the State preserves of loaves and fishes, that things in general were settled for ever.</p>
      <div class="p-8 mb-4 text-center">
        <button @click="showAnnouncement = true" type="button" class="btn btn-blue">Open Modal</button>
      </div>
      <p
        class="mb-6"
      >It was the year of Our Lord one thousand seven hundred and seventy-five. Spiritual revelations were conceded to England at that favoured period, as at this. Mrs. Southcott had recently attained her five-and-twentieth blessed birthday, of whom a prophetic private in the Life Guards had heralded the sublime appearance by announcing that arrangements were made for the swallowing up of London and Westminster. Even the Cock-lane ghost had been laid only a round dozen of years, after rapping out its messages, as the spirits of this very year last past (supernaturally deficient in originality) rapped out theirs. Mere messages in the earthly order of events had lately come to the English Crown and People, from a congress of British subjects in America: which, strange to relate, have proved more important to the human race than any communications yet received through any of the chickens of the Cock-lane brood.</p>
      <p
        class="mb-6"
      >France, less favoured on the whole as to matters spiritual than her sister of the shield and trident, rolled with exceeding smoothness down hill, making paper money and spending it. Under the guidance of her Christian pastors, she entertained herself, besides, with such humane achievements as sentencing a youth to have his hands cut off, his tongue torn out with pincers, and his body burned alive, because he had not kneeled down in the rain to do honour to a dirty procession of monks which passed within his view, at a distance of some fifty or sixty yards. It is likely enough that, rooted in the woods of France and Norway, there were growing trees, when that sufferer was put to death, already marked by the Woodman, Fate, to come down and be sawn into boards, to make a certain movable framework with a sack and a knife in it, terrible in history. It is likely enough that in the rough outhouses of some tillers of the heavy lands adjacent to Paris, there were sheltered from the weather that very day, rude carts, bespattered with rustic mire, snuffed about by pigs, and roosted in by poultry, which the Farmer, Death, had already set apart to be his tumbrils of the Revolution. But that Woodman and that Farmer, though they work unceasingly, work silently, and no one heard them as they went about with muffled tread: the rather, forasmuch as to entertain any suspicion that they were awake, was to be atheistical and traitorous.</p>
    </div>
    <announcement-modal :show="showAnnouncement" @close="showAnnouncement = false"></announcement-modal>
    <portal-target name="modals"></portal-target>

    <!-- Slots -->
    <div class="text-center p-8 my-8">
      <primary-button>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
          <path d="M13 8V2H7v6H2l8 8 8-8h-5zM0 18h20v2H0v-2z"></path>
        </svg>
        Download
      </primary-button>
    </div>

    <div class="max-w-xs mx-auto mb-8">
      <media-card>
        <img
          slot="image"
          src="https://images.unsplash.com/photo-1495835788122-ca48931258be?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=acc48b0187b28f7a221362b843f15755&auto=format&fit=crop&w=700&q=80"
        >
        <template slot="heading">The Long Road to Mastering the Perfect Cartwheel</template>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia eos accusantium minima architecto natus sequi quisquam incidunt dolorem, adipisci accusamus facere dicta magni, qui consectetur, omnis quis, voluptas tempore quo!</p>
      </media-card>
    </div>

    <div class="max-w-xs mx-auto mb-8">
      <media-card>
        <template slot="heading">Crossing the Street for Dummies</template>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia eos accusantium minima architecto natus sequi quisquam incidunt dolorem, adipisci accusamus facere dicta magni, qui consectetur, omnis quis, voluptas tempore quo!</p>
        <img
          slot="image"
          src="https://images.unsplash.com/photo-1490855137152-82177ecaf6e4?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=2929d63d861df6513b9e1e34196f71a2&auto=format&fit=crop&w=700&q=60"
        >
      </media-card>
    </div>

    <div class="max-w-xs mx-auto mb-8">
      <media-card>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia eos accusantium minima architecto natus sequi quisquam incidunt dolorem, adipisci accusamus facere dicta magni, qui consectetur, omnis quis, voluptas tempore quo!</p>
        <img
          slot="image"
          src="https://images.unsplash.com/photo-1490855137152-82177ecaf6e4?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=2929d63d861df6513b9e1e34196f71a2&auto=format&fit=crop&w=700&q=60"
        >
      </media-card>
    </div>
    <!-- End slots -->

    <!-- Contact list -->
    <div class="max-w-sm mx-auto">
      <fetch-json url="../static/contacts.json" class="mb-8">
        <contact-list slot-scope="{ response: contacts }" :contacts="contacts"></contact-list>
      </fetch-json>
    </div>
    <!-- End contact list -->

    <!-- Death metal  albums -->
    <div class="max-w-sm mx-auto">
      <fetch-json url="../static/albums.json">
        <div class="card" slot-scope="{ response: albums, loading }">
          <h1 class="text-2xl font-bold mb-6">Top Death Metal Albums</h1>
          <div v-if="loading" class="text-grey-darker">Loading...</div>
          <div v-else>
            <div class="album-grid">
              <div class="album-grid-item" v-for="album in albums" :key="album.id">
                <img :src="`/static${album.artwork}`">
                <h2 class="album-title">{{ album.title }}</h2>
                <p class="album-artist">{{ album.artist }}</p>
              </div>
            </div>
          </div>
        </div>
      </fetch-json>
    </div>
    <!-- End death metal albums -->

    <div class="text-center p-8 my-8">
      <hello-world>
        <h1 slot-scope="{ subject }">Hello {{ subject }}!</h1>
      </hello-world>
    </div>

    <!-- Tag input -->
    <div class="max-w-sm mx-auto card mt-8">
      <label class="form-label mb-2">Original Tag Input</label>
      <tag-input v-model="tags"></tag-input>
    </div>
    <!-- End tag input -->

    <!-- Renderless tag input -->
    <div class="max-w-sm mx-auto card mt-8">
      <label class="form-label mb-2">Renderless Tag Input</label>
      <renderless-tag-input v-model="tags">
        <div class="tag-input" slot-scope="{ tags, removeTag }">
          <span v-for="tag in tags" :key="tag" class="tag-input-tag">
            <span>{{ tag }}</span>
            <button type="button" class="tag-input-remove" @click="removeTag(tag)">&times;</button>
          </span>
          <input class="tag-input-text" placeholder="Add tag...">
        </div>
      </renderless-tag-input>
    </div>
    <!-- End renderless tag input -->
  </div>
</template>

<script>
import UserSettingsForm from './components/UserSettingsForm.vue'
import DatePicker from './components/DatePicker.vue'
import AnnouncementModal from './components/AnnouncementModal.vue'
import PrimaryButton from './components/PrimaryButton.vue'
import MediaCard from './components/MediaCard.vue'
import ContactList from './components/ContactList.vue'
import FetchJson from './components/FetchJson.vue'
import HelloWorld from './components/HelloWorld.vue'
import TagInput from './components/TagInput.vue'
import RenderlessTagInput from './components/RenderlessTagInput.vue'

export default {
  data() {
    return {
      date: null,
      accountId: 7,
      showAnnouncement: true,
      tags: ['awesome', 'excellent', 'amazing'],
    }
  },
  components: {
    UserSettingsForm,
    DatePicker,
    AnnouncementModal,
    PrimaryButton,
    MediaCard,
    ContactList,
    FetchJson,
    HelloWorld,
    TagInput,
    RenderlessTagInput,
  },
}
</script>

<style src="./assets/css/app.css"/>
