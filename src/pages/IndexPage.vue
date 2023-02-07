<template>
  <div class="q-pa-md">
    <q-carousel
      v-model="slide"
      swipeable
      animated
      :padding="padding"
      :vertical="vertical"
      :arrows="arrows"
      :navigation="navigation"
      :navigation-position="navPos"
      height="auto"
      class="text-black rounded-borders"
    >
      <q-carousel-slide name="style" class="column no-wrap flex-center">
        <q-img
          :src="url"
          spinner-color="white"
          style="height: 140px; max-width: 150px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="tv" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/quasar-logo-inner.svg"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="layers" class="column no-wrap flex-center">
        <q-icon name="layers" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="map" class="column no-wrap flex-center">
        <q-icon name="terrain" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
  setup() {
    const navPos = ref('top');
    const vertical = ref(false);
    const url = ref('https://cdn.quasar.dev/img/mountains.jpg');

    watch(vertical, (val) => {
      navPos.value = val === true ? 'right' : 'top';
    });

    return {
      padding: ref(true),
      vertical,
      arrows: ref(true),
      navigation: ref(true),

      navPos,
      navigationPositions: [
        { value: 'top', label: 'top' },
        { value: 'right', label: 'right' },
        { value: 'bottom', label: 'bottom (default)' },
        { value: 'left', label: 'left' },
      ],

      url,
      refresh() {
        url.value = 'https://cdn.quasar.dev/img/mountains.jpg' + Math.random();
      },

      slide: ref('style'),
      lorem:
        'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.',
    };
  },
};
</script>
