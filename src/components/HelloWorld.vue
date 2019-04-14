<script>
import PrimaryButton from './PrimaryButton.vue'
import ToggleInput from './ToggleInput.vue'

export default {
  data() {
    return {
      toggled: true,
    }
  },
  render(createElement) {
    return createElement(ToggleInput, {
      props: {
        toggled: this.toggled,
      },
      on: {
        toggle: newValue => (this.toggled = newValue),
      },
    })
  },
}
</script>
