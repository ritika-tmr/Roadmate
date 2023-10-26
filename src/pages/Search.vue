<template>
  <q-page>
    <div class="q-ma-sm">
    <h6 class="q-my-none" ><q-icon name="place" /> Parramatta, Sydney</h6>
  </div>
    <div class="row no-wrap q-ma-sm">
      <q-input class="full-width" dense borderless filled v-model="text" label="Search" />
      <q-btn class="q-ml-sm" unelevated dense color="primary" icon="tune" />
    </div>
    <div class="q-pa-md">
      <q-chip clickable color="grey-2" icon-right="star" label="Rating" />
      <q-chip clickable color="grey-2" icon-right="directions" label="Distance" />
      <q-chip clickable color="grey-2" icon-right="attach_money" label="Price" />
      <q-chip clickable color="grey-2" icon-right="schedule" label="Time" />
      <q-chip clickable icon-right="expand_more" label="Sort" />
      <q-chip clickable icon-right="view_list" />
    </div>
    <service-card
      title="NRMA"
      address="Parramatta"
      rating="4.5"
      img="src/assets/service-icons/image 4.png"
      @click="$router.push('details/NRMA')"
    ></service-card>
    <service-card
      title="RAC Roadside Assistance"
      address="Liverpool"
      rating="4.0"
      img="src/assets/service-icons/image 2.png"
      @click="$router.push('details/RAC')"></service-card>
    <service-card
      title="Batteries on the GO"
      address="Blacktown"
      rating="4.5"
      img="src/assets/service-icons/image 3.png"
      @click="$router.push('Details/Batteries on the GO')"></service-card>
    <service-card title="24/7 RoadServices Australia" address="Surrey Hills" rating="4.5" img="src/assets/service-icons/image 5.png" @click="$router.push('Details')"></service-card>
    <service-card title="Roadside Response" address="Penrith" rating="2.5" img="src/assets/service-icons/image 6.png" @click="$router.push('Details')"></service-card>
    <service-card title="Allianz Roadside Assistance" address="Parramatta" rating="4.5" img="src/assets/service-icons/Rectangle 1725.png" @click="$router.push('Details')"></service-card>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import serviceCard from 'components/ServiceCard.vue'

export default defineComponent({
  name: 'SearchPage',
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
