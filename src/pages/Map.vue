<template>
  <q-page>
    <h6 class="q-my-none"><q-icon name="place" /> Parramatta, Sydney</h6>
    <div>
      <GMapAutocomplete
        placeholder="Search Roadmate"
        @place_changed="setPlace($event)"
      >
      </GMapAutocomplete>
      <GMapMap
        :center="center"
        :zoom="15"
        map-type-id="terrain"
        style="width: 100vw; height: 70vh"
        draggable="false"
        @click="mapPoint($event)"
      >
        <GMapCircle
          :key="index"
          v-for="(m, index) in markers"
          :radius="50"
          :center="{ lat: m.position.lat, lng: m.position.lng}"
          :options="circleOptions"
        />
      </GMapMap>
    </div>
    <div>
      <q-card class="bg-white">
        <q-card-section>
          <div class="row justify-between">
            <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
            <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
            <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
            <hot-key title="Flat tire" icon="tire_repair" @click="$router.push('Search')"></hot-key>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import hotKey from 'components/HotKey.vue'
export default defineComponent({
  name: 'BookedPage',
  components: {
    hotKey
  },
  setup () {
    return {
      center: { lat: -33.814785, lng: 151.0017218 },
      position: {
        lat: -33.814785,
        lng: 151.0017218
      },
      position_car: {
        lat: -33.814785,
        lng: 151.0017218
      },
      markers: [
        {
          position: {
            lat: -33.817235134357134,
            lng: 151.0048484802246
          }
        },
        {
          position: {
            lat: -33.81738461893973,
            lng: 151.01190132017723
          }
        },
        {
          position: {
            lat: -33.81349129826598,
            lng: 151.00939750671387
          }
        },
        {
          position: {
            lat: -33.81013953456771,
            lng: 151.00420475006104

          }
        }
      ],
      circleOptions: {
        strokeColor: '#FF0000',
        strokeOpacity: 0.8,
        strokeWeight: 2,
        fillColor: '#FF0000',
        fillOpacity: 0.35
      }
    }
  },
  methods: {
    setPlace (place) {
      console.log('place', place)
      this.center = {
        lat: place.geometry.location.lat(),
        lng: place.geometry.location.lng()
      }
      this.position = {
        lat: place.geometry.location.lat(),
        lng: place.geometry.location.lng()
      }
    },
    mapPoint (place) {
      // this.map.push(
      //   position: {
      //   lat: place.latLng.lat(),
      //   lng: place.latlng.lng()
      // })
      console.log('place', place.latLng.lat(), place.latLng.lng())
    }
  }
})
</script>
