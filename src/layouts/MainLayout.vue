<template>
  <q-layout>
    <q-footer>
        <q-tabs
          v-model="tab"
          dense
          active-color="primary"
          align="justify"
          class="bg-white text-grey "
          :breakpoint="0"
        >
        <q-tab name="mails" icon="mail" />
        <q-tab name="alarms" icon="alarm" />
        <q-tab name="movies" icon="movie" />
        <q-tab name="home" icon="movie" />
        <q-tab name="chat" icon="movie" />

        </q-tabs>
    </q-footer>
    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'MainLayout',
  setup () {
    return {
      tab: ref('mails')
    }
  }
})
</script>
