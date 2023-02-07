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
      class="bg-white text-black rounded-borders"
    >
      <q-carousel-slide name="style" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/human.png"
          style="width: 200px; height: 140px"
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
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/peanut.png"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="head" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/human-head.png"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="trash" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/human-trash.png"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="gold" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/gold.png"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="warning" class="column no-wrap flex-center">
        <div class="q-mt-md title text-center">HYGIENE RULES</div>
        <div class="text-center">Prambanan Factory</div>
        <img
          alt="Quasar logo"
          src="~assets/warning.png"
          style="width: 200px; height: 140px"
        />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
        <div class="q-mt-md">
          <q-btn rounded color="primary" label="Next" />
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
