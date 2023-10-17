<template>
  <q-card flat class="my-card q-ma-sm bg-grey-2">
    <q-card-section>
      <q-item>
      <q-item-section v-if="img" avatar>
        <q-avatar>
          <img :src="img">
        </q-avatar>
      </q-item-section>

      <q-item-section>
        <div class="row items-center no-wrap">
          <div class="col">
            <q-item-label>{{ title }}</q-item-label>
            <q-item-label caption>{{ address }}</q-item-label>
          </div>
          <div class="col-auto">
            <q-icon color="yellow" name="star"/>
            <a>{{ rating }}</a>
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
            <a>$ {{ price }}</a>
          </div>
        </div>
      </q-item-section>
    </q-item>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ServiceCard',
  props: {
    title: {
      type: String,
      required: true
    },

    address: {
      type: String,
      default: ''
    },
    img: {
      type: String,
      default: ''
    },
    icon: {
      type: String,
      default: ''
    },
    price: {
      type: String,
      default: '50'
    },
    rating: {
      type: String,
      default: '4'
    },
    time: {
      type: String,
      default: '10-15'
    },
    distance: {
      type: String,
      default: '5'
    }
  }
})
</script>
