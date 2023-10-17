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
        <q-tab name="chat" icon="chat" />
        <q-tab name="history" icon="receipt" />
        <q-tab name="home" icon="home" @click="$router.push('/')"/>
        <q-tab name="notification" icon="notifications" />
        <q-tab name="profile" icon="person" />
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
      tab: ref('home')
    }
  }
})
</script>
