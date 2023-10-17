<template>
  <q-page>
    <div class="q-ma-sm">
    <h6 class="q-my-none"><q-icon name="place" /> Parramatta, Sydney</h6>
  </div>
    <div class="row no-wrap q-ma-sm">
      <q-input class="full-width" dense borderless filled v-model="text" label="Search" />
      <q-btn class="q-ml-sm" unelevated dense color="primary" icon="tune" />
    </div>
    <div class="q-pa-md">
      <q-chip clickable color="grey-2" icon="event">
        Add to calendar
      </q-chip>
      <q-chip clickable color="grey-2" icon="bookmark">
        Bookmark
      </q-chip>
      <q-chip clickable color="grey-2" icon="bookmark">
        Bookmark
      </q-chip>
      <q-chip clickable color="grey-2" icon="alarm" label="Set alarm" />
      <q-chip clickable icon="directions">
        Get directions
      </q-chip>
    </div>
    <service-card title="NRMA" address="Parramatta" rating="4.5"></service-card>
    <service-card title="NRMA" address="Parramatta" rating="4.5"></service-card>
    <service-card title="NRMA" address="Parramatta" rating="4.5"></service-card>
    <service-card title="NRMA" address="Parramatta" rating="4.5"></service-card>
    <service-card title="NRMA" address="Parramatta" rating="4.5"></service-card>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import serviceCard from 'components/ServiceCard.vue'
export default defineComponent({
  name: 'IndexPage',
  components: {
    serviceCard
  },
  setup () {
    return {
      text: ref('')
    }
  }
})
</script>
