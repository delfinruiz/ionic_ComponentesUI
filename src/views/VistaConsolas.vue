<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title><h1>Consolas</h1></ion-title>
       </ion-toolbar>
    </ion-header>  
    
    <ion-content class="ion-padding">
      <ion-grid>
        <ion-row>
          <ion-col v-for="(consola, i) in consolas" :key="i">
              <ion-card>
                <center><img :src="consola.imagen" alt="" width="50" height="50" style="margin: 30px;"></center>
                <ion-card-header>
                  <ion-card-title>{{ consola.nombre }}</ion-card-title>
                  <ion-card-subtitle>Juegos de {{ consola.nombre }}</ion-card-subtitle>
                </ion-card-header>
                <ion-card-content>{{ consolas.descripcion }}</ion-card-content>
                <ion-button :router-link="`/tabs/juego/${consola.nombre}/${consola.id}`" color="dark" size="full" expand="full">Explorar Juegos</ion-button>
              </ion-card>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-content>
  </ion-page>
</template>

<script>
import {IonPage, IonHeader, IonToolbar, IonContent, IonTitle, IonGrid, IonRow, IonCol, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent,
  IonButton
} from '@ionic/vue';

export default{

  name: 'VistaConsolas',
  components: {
    IonPage, IonHeader, IonToolbar, IonContent, IonTitle, IonGrid, IonRow, IonCol, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent,
    IonButton
  },
  data(){
    return{
      consolas:[
        {id:1, nombre: 'PlayStation', descripcion: 'Juegos Exclusivos para PlayStation', imagen: '/LogoPlaystation.png'},
        {id:2, nombre: 'Xbox', descripcion: 'Juegos Exclusivos para Xbox', imagen: '/LogoXbox.png'},
        {id:3, nombre: 'Nintendo', descripcion: 'Juegos Exclusivos para Nintendo', imagen: '/LogoNintendo.png'}
      ]
    }
  }
}

</script>

<style scoped>

</style>
