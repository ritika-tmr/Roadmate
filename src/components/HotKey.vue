<template>
  <q-card flat class="my-card q-my-sm bg-grey-2">
    <q-card-section>
      <q-btn class="q-ml-sm" unelevated dense color="primary" icon="tune" />
    </q-card-section>
    <q-item>
      <q-item-section>
        <q-item-label>{{ title }}</q-item-label>
      </q-item-section>
    </q-item>
  </q-card>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HotKey',
  props: {
    title: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      default: ''
    }
  }
})
</script>
