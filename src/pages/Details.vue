<template>
  <q-page class="q-pa-sm">
    <q-card flat class="my-card q-ma-sm">
      <q-card-section>
        <q-item>
          <q-item-section v-if="img" avatar>
            <img :src="img">
          </q-item-section>
          <q-item-section>
            <div class="row items-center no-wrap">
              <div class="col">
                <q-item-label>{{ title }}</q-item-label>
                <q-icon color="yellow" name="star"/>
                <a>{{ rating }}</a>
              </div>
              <div class="col-auto">
                <div>Flat Tyre</div>
              </div>
            </div>
            <div class="row items-center no-wrap">
              <div class="col">
                <q-btn color="primary" unelevated icon="chat" />
                <q-btn color="info" unelevated icon="call" />
              </div>
              <div class="col-auto">
                <a>$ {{ price }}</a>
              </div>
            </div>
          </q-item-section>
        </q-item>
      </q-card-section>
    </q-card>
    <div>
      <q-item-label>About {{ title }}</q-item-label>
      <q-item-label caption> NRMA Insurance is part of the Insurance Australia Group. </q-item-label>
    </div>
    <div>
      <q-item-label>Location</q-item-label>
      <q-item-label caption> 3891 Ranchview Dr. Richardson,
        San Francisco 62639 </q-item-label>
      <div >
        <GMapMap
          :center="center"
          :zoom="15"
          map-type-id="terrain"
          style="width: 100vw; height: 50vh"
        >
          <GMapCluster :zoomOnClick="true">
            <GMapMarker
              :key="index"
              v-for="(m, index) in markers"
              :position="m.position"
              :clickable="false"
              :draggable="false"
            />
          </GMapCluster>
        </GMapMap>
      </div>
    </div>
    <div>
      <q-item-label>Reviews</q-item-label>
      <q-card flat class="my-card q-ma-sm bg-grey-2">
        <q-card-section>
          <a>John Doe</a>
          <q-rating
            v-model="ratingModel"
            size="1em"
          />
          <q-item-label caption>It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.</q-item-label>
        </q-card-section>
      </q-card>
      <q-card flat class="my-card q-ma-sm bg-grey-2">
        <q-card-section>
          <a>John Doe</a>
          <q-rating
            v-model="ratingModel"
            size="1em"
          />
          <q-item-label caption>It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.</q-item-label>
        </q-card-section>
      </q-card>
      <q-card flat class="my-card q-ma-sm bg-grey-2">
        <q-card-section>
          <a>John Doe</a>
          <q-rating
            v-model="ratingModel"
            size="1em"
          />
          <q-item-label caption>It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.</q-item-label>
        </q-card-section>
      </q-card>
      <q-card flat class="my-card q-ma-sm bg-grey-2">
        <q-card-section>
          <a>John Doe</a>
          <q-rating
            v-model="ratingModel"
            size="1em"
          />
          <q-item-label caption>It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.</q-item-label>
        </q-card-section>
      </q-card>
    </div>
    <div class="row no-wrap">
    <q-btn class="full-width" color="primary" unelevated icon-right="send" label="Book Assistance" @click="$router.push('/Booked')" />
    <q-btn class="q-ml-sm" unelevated color="primary" icon="timer" />
    </div>
  </q-page>
</template>

<script>

import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'DetailsPage',
  setup () {
    return {
      text: ref(''),
      title: 'NRMA',
      img: 'src/assets/service-icons/image 4.png',
      address: 'Parramatta',
      rating: 4.5,
      time: 10,
      distance: 1,
      price: 50,
      id: 1,
      ratingModel: ref(4),
      center: { lat: -33.814785, lng: 151.0017218 },
      markers: [
        {
          position: {
            lat: -33.814785,
            lng: 151.0017218
          }
        }
      ]
    }
  },
  created () {
    console.log('id', this.$route.params.title)
    this.title = this.$route.params.title
  },
  watch: {
    title (val) {
      switch (this.title) {
        case 'NRMA':
          this.img = 'src/assets/service-icons/image 4.png'
          break
        case 'RAC':
          this.img = 'src/assets/service-icons/image 2.png'
          break
        case 'Batteries on the GO':
          this.img = 'src/assets/service-icons/image 3.png'
          break
      }
    }
  }
})
</script>
