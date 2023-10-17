<template>
  <q-page class="q-pa-sm">
    <div class="q-ma-sm">
      <h4 class="q-my-none">Welcome, Mark!</h4>
    </div>
    <div class="q-ma-sm">
      <h6 class="q-my-none"><q-icon name="place" /> Parramatta, Sydney</h6>
    </div>
    <div class="row no-wrap q-ma-sm">
      <q-input class="full-width" dense borderless filled v-model="text" label="Search" />
      <q-btn class="q-ml-sm" unelevated dense color="primary" icon="tune" />
    </div>
    <div class="row justify-between">
      <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
      <hot-key title="Flat tire" icon="tire_repair"></hot-key>
    </div>
    <div class="q-ma-sm">
      <q-btn class="full-width" unelevated color="primary" icon="group_add" icon-right="send" label="Make an Appointment" />
    </div>
    <div class="row justify-between">
      <h5>Recent</h5>
      <q-btn flat label="See All" />
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
import hotKey from 'components/HotKey.vue'
import serviceCard from 'components/ServiceCard.vue'

export default defineComponent({
  name: 'IndexPage',
  components: {
    hotKey,
    serviceCard
  },
  setup () {
    return {
      text: ref('')
    }
  }
})
</script>
