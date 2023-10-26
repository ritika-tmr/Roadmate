<template>
  <q-page>
    <q-inner-loading
      :showing="visible"
      label="Please wait..."
      label-class="text-teal"
      label-style="font-size: 1.1em"
    />
    <h6 class="q-ma-sm"><q-icon name="place" /> Parramatta, Sydney</h6>
    <div>
      <GMapMap
        :center="center"
        :zoom="15"
        map-type-id="terrain"
        style="width: 100vw; height: 55vh"
      >
        <GMapCluster :zoomOnClick="true">
          <GMapMarker
            :key="index"
            v-for="(m, index) in markers"
            :position="m.position"
            :clickable="false"
            :draggable="false"
          />
          <GMapCircle
            :key="index"
            v-for="(m, index) in marker"
            :radius="30"
            :center="{ lat: m.position.lat, lng: m.position.lng}"
            :options="circleOptions"
          />
        </GMapCluster>
      </GMapMap>
    </div>
    <div>
      <q-card class="bg-primary">
        <q-card-section>
          <q-item-label class="text-white">Check your service, every time</q-item-label>
          <q-item-label class="text-white" caption>Always check the license plate, car details, and match the driver’s photo</q-item-label>
        </q-card-section>
      </q-card>
      <q-card flat class="bg-white">
        <q-card-section>
          <div class="row items-center no-wrap">
            <div>
              <img src="src/assets/service-icons/image%204.png">
            </div>
            <div class="col">
              <q-item-label>{{ title }}</q-item-label>
              <q-icon color="yellow" name="star"/>
              <a>{{ rating }}</a>
            </div>
            <div class="col-auto">
              <q-item-label>John Doe</q-item-label>
            </div>
          </div>
          <div class="row items-center no-wrap">
            <div class="col">
              <q-item-label caption>
                <q-icon name="schedule" />
                {{ time }} min
                <q-icon name="sync_alt"/>
                {{ distance }} km
              </q-item-label>
            </div>
            <div class="col-auto">
              <a>ABC1012</a>
            </div>
          </div>
          <q-card-actions>
            <div class="row no-wrap q-ma-sm">
              <q-btn class="q-mr-sm" unelevated rounded dense color="grey-3" icon="call" />
              <q-input class="full-width" rounded standout dense borderless filled label="Any notes" />
            </div>
            <q-btn flat color="grey" label="Cancel reservation" @click="$router.push('/')" />
          </q-card-actions>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'BookedPage',
  setup () {
    return {
      center: { lat: -33.814785, lng: 151.0017218 },
      markers: [
        {
          position: {
            lat: -33.814785,
            lng: 151.0017218
          }
        }
      ],
      title: 'NRMA',
      address: 'Parramatta, Sydney',
      rating: 4.5,
      time: 30,
      distance: 10,
      price: 50,
      position_car: {
        lat: -33.814785,
        lng: 151.0017218
      },
      visible: true,
      marker: [
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
  created () {
    this.showTextLoading()
  },
  methods: {
    showTextLoading () {
      console.log('please wait')
      setTimeout(() => {
        this.visible = false
      }, 3000)
    }
  }
})
</script>
