<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> GPS | geolocation </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <div class="p-3">
        <button class="btn btn-primary btn-lg w-100" @click="getGeo()">Get Geolocation</button>
         <div class="mt-4">
                <p>Latitude</p>
                <input v-model="coords.latitude" class="form-control" type="text" />
              </div>
             <div>
            <p>Longitude</p>
         <input v-model="coords.longitude" class="form-control" type="text" />
      </div>
    </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Geolocation } from '@capacitor/geolocation';
import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonIcon,
  IonRouterOutlet,
} from '@ionic/vue';

export default defineComponent({
  name: 'geolocationScreen',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonIcon,
    IonRouterOutlet,
  },
   data() {
        return {
         coords: {} as any
     }
    },
    methods: {
        async getGeo() {
         const coordinates = await Geolocation.getCurrentPosition();
         this.coords = coordinates.coords;
      }
    }
});
</script>

<style scoped>
.banner {
  width: 100vw;
  height: 260px;
  object-fit: cover;
  object-position: center;
}
</style>
