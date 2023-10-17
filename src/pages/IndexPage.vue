<template>
  <q-page>
    <div class="q-ma-sm">
      <h4 class="q-my-none">Welcome, Mark!</h4>
    </div>
    <div class="q-ma-sm">
      <h6 class="q-my-none"><q-icon name="place" /> Parramatta, Sydney</h6>
    </div>
    <div class="row no-wrap q-ma-sm">
      <q-input class="full-width" dense borderless filled v-model="text" label="Search" />
      <q-btn dense color="primary" icon="tune" />
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  setup () {
    return {
      text: ref('')
    }
  }
})
</script>
