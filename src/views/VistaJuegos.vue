<template>
  <ion-page>

    <ion-header>
      <ion-toolbar>
        <ion-buttons>
          <ion-back-button>Volver</ion-back-button>
        </ion-buttons>
        <ion-title>Juegos</ion-title>
      </ion-toolbar>
    </ion-header>  

    <ion-content class="ion-padding">
      <ion-card>
        <ion-card-header>
          <ion-card-title>Juegos de {{ this.$route.params.consola }}</ion-card-title>
          <ion-card-subtitle>Listado de Video Juegos</ion-card-subtitle>
        </ion-card-header>

        <ion-card-content>
          <ion-list lines="none">
            <template v-for="(juego, i) in juegos" :key="i">
              <ion-item v-if="juego.consola===this.$route.params.consola">
                <ion-thumbnail>
                  <img :src="juego.imagen" alt="portada">
                </ion-thumbnail>

                <ion-label>{{ juego.nombre }}</ion-label>
                <ion-button fill="clear" color="danger" @click="ShowAlert(true, i)">
                  <ion-icon :icon="heart"></ion-icon>
                </ion-button>

                <ion-button fill="clear" color="warning" @click="ShowToast(true, i)">
                  <ion-icon :icon="addCircle"></ion-icon>
                </ion-button>

              </ion-item>

              <ion-alert header="Notificacion" sub-header="Exito" message="Juego añadido a favoritos" :is-open="alertState[i]" @didDismiss="ShowAlert(false, i)" />
              <ion-toast header="Notificacion" sub-header="Exito" message="Juego añadido a favoritos" :is-open="toastState[i]" @didDismiss="ShowToast(false, i)" :duration="2000"/>

            </template>
          </ion-list>
        </ion-card-content>
      </ion-card>
    </ion-content>
  
  </ion-page>
</template>

<script>
import {IonPage, IonHeader, IonToolbar, IonButtons, IonBackButton, IonContent, IonCard, IonCardHeader, IonTitle, IonCardSubtitle, IonCardContent, IonList, IonCardTitle,
  IonThumbnail, IonLabel, IonItem, IonIcon, IonAlert, IonButton, IonToast
} from '@ionic/vue';

import {heart, addCircle} from 'ionicons/icons';

export default{

  name: 'VistaJuegos',
  components: {
    IonPage, IonHeader, IonToolbar, IonButtons, IonBackButton, IonContent, IonCard, IonCardHeader, IonTitle, IonCardSubtitle, IonCardContent, IonList, IonCardTitle,
    IonThumbnail, IonLabel, IonItem, IonIcon, IonAlert, IonButton, IonToast
  
  },
  data(){
    return{
      heart, addCircle,
      alertState: [],
      toastState: [],
      juegos:[
                {consola:'PlayStation' , nombre:'UFC 5', imagen:'/juego_PS1.png'},
                {consola:'PlayStation' , nombre:'God Of War Ragnarok', imagen:'/juego_PS2.png'},
                {consola:'PlayStation' , nombre:'Spider-Man 2',  imagen:'/juego_PS3.png'},
                {consola:'Xbox' , nombre:'Mortal Combat X', imagen:'/juego_XB1.png'},
                {consola:'Xbox' , nombre:'Hitmat HD Trilogy', imagen:'/juego_XB2.png'},
                {consola:'Xbox' , nombre:'Assasin Creed Revelation', imagen:'/juego_XB3.png'},
                {consola:'Nintendo' , nombre:'The Legend Of Zelda: Breath of the Wild',  imagen:'/juego_NS1.png'},
                {consola:'Nintendo' , nombre:'Super Mario Odyssey', imagen:'/juego_NS2.png'}, 
                {consola:'Nintendo' , nombre:'Pokemon Violet', imagen:'/juego_NS3.png'}
                
      ]
    }
  },
  methods:{
    ShowAlert(state, i){
      this.alertState[i] = state
    },
    ShowToast(state, i){
      this.toastState[i] = state
    }
  }
}

</script>

<style scoped>

</style>
