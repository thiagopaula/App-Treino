<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Nome App
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <dark-mode-toogle />

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, onMounted } from 'vue'
import DarkModeToogle from 'components/DarkModeToggle.vue'
import useApi from 'src/composables/UseApi'

export default defineComponent({
  name: 'LoginLayout',

  components: {
    DarkModeToogle
  },

  setup () {
    const { getBrand } = useApi()
    onMounted(() => {
      getBrand()
    })
    return {
    }
  }
})
</script>
