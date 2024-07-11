<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar>
        <ion-tab-button tab="inicio" href="/tabs/inicio">
          <ion-icon :icon="home"></ion-icon>
          <ion-label>Inicio</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="consolas" href="/tabs/consolas">
          <ion-icon :icon="gameController"></ion-icon>
          <ion-label>Consolas</ion-label>
        </ion-tab-button>

      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script>
import {IonPage, IonRouterOutlet, IonTabs, IonTabButton, IonIcon, IonLabel, IonTabBar} from '@ionic/vue';
import {home, gameController} from 'ionicons/icons';
export default{
  name: 'VistaTabs',
  components: {IonPage, IonRouterOutlet, IonTabs, IonTabButton, IonIcon, IonLabel, IonTabBar},
  data(){
  return{
    home, gameController
  }
}
}


</script>

<style scoped>

</style>
