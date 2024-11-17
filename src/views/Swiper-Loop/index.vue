<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Swiper Loop Screen</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <swiper :slides-per-view="1" :space-between="50" @swiper="onSwiper">
        <swiper-slide v-for="(banner, i) in banners" :key="i">
          <img class="banner" :src="banner" />
        </swiper-slide>
      </swiper>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

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
  name: 'swiperloopScreen',
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
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiper: {} as any,
      banners: [
        'https://static.vecteezy.com/system/resources/previews/000/272/740/original/vector-colorful-circle-banner-template-horizontal-advertising-business-banner.jpg',
        'https://cdn.kwork.com/pics/t3/26/31846904-65db133e3bd44.jpg',
        'https://i.pinimg.com/originals/fb/3a/45/fb3a457cb762c268aa83a73047d5b3d9.jpg',
        'https://cdn.kwork.com/files/portfolio/t3/90/45dbbf8bd3955a17ecfc6c7927719ae5200ed098-1708857109.jpg',
        'https://designshifu.com/wp-content/uploads/2022/11/Ad-banner-design-ideas-examples-that-get-the-maximum-clicks.jpg',
        'https://mir-s3-cdn-cf.behance.net/project_modules/2800_opt_1/706c66103003811.5f43ca98674fe.jpg',
      ],
    };
  },
  methods: {
    async onSwiper(event: any) {
      this.swiper = event;
    },
  },
  setup() {
    return {
      menu,
      home,
      person,
    };
  },
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
