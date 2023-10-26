<template>
  <q-page class="q-pa-sm">
    <div class="q-ma-sm">
      <h5 class="q-my-none">Welcome, Mohammad!</h5>
    </div>
    <div class="q-ma-sm" @click="$router.push('/Map')">
      <h6 class="q-my-none"><q-icon name="place" /> Parramatta, Sydney</h6>
    </div>
    <div class="row no-wrap q-ma-sm">
      <q-input class="full-width" dense borderless filled v-model="text" label="Search" />
      <q-btn class="q-ml-sm" unelevated dense color="primary" icon="tune" />
    </div>
    <div class="row justify-between">
      <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
      <hot-key title="Key" icon="car_rental"  @click="$router.push('Search')"></hot-key>
      <hot-key title="Fuel" icon="local_gas_station"  @click="$router.push('Search')"></hot-key>
      <hot-key title="Repair" icon="car_repair"  @click="$router.push('Search')"></hot-key>
      <hot-key title="Battery" icon="charging_station"  @click="$router.push('Search')"></hot-key>
      <hot-key title="Accident" icon="car_crash"  @click="$router.push('Search')"></hot-key>
      <hot-key title="Towing" icon="fire_truck"  @click="$router.push('Search')"></hot-key>
      <hot-key title="More" icon="more_horiz"  @click="$router.push('Search')"></hot-key>
    </div>
    <div class="q-ma-sm">
      <q-btn class="full-width" unelevated color="primary" icon="group_add" icon-right="send" label="Make an Appointment" />
    </div>
    <div class="row justify-between">
      <h5>Recent</h5>
      <q-btn flat label="See All" />
    </div>
    <service-card title="NRMA" address="Parramatta" rating="4.5" img="src/assets/service-icons/image 4.png"></service-card>
    <service-card title="RAC Roadside Assistance" address="Liverpool" rating="4.0" img="src/assets/service-icons/image 2.png"></service-card>
    <service-card title="Batteries on the GO" address="Blacktown" rating="4.5" img="src/assets/service-icons/image 3.png"></service-card>
    <service-card title="24/7 RoadServices Australia" address="Surrey Hills" rating="4.5" img="src/assets/service-icons/image 5.png"></service-card>
    <service-card title="Roadside Response" address="Penrith" rating="2.5" img="src/assets/service-icons/image 6.png"></service-card>
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
