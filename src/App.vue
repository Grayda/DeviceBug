<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';

import { Device } from '@capacitor/device'

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  },
  mounted() {
    Device.getBatteryInfo().then((info) => {
      alert("Battery info: " + JSON.stringify(info))
    })
  }
});
</script>