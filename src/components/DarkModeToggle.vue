<script>
import { defineComponent, ref, onMounted } from 'vue'
import { useQuasar } from 'quasar'

export default defineComponent({
  setup () {
    const darkMode = ref(true)
    const $q = useQuasar()

    onMounted(() => {
      $q.dark.set(true)
      $q.localStorage.set('darkMode', darkMode)
      const darkModeIsActive = $q.localStorage.getItem('darkMode')
      if (darkModeIsActive) {
        darkMode.value = false
      }
    })

    return {
      darkMode
    }
  }
})
</script>
