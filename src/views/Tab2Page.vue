<template>
  <ion-page>
    
    <ion-content :fullscreen="true">
      
      <ExploreContainer name="Tab 2 page" />
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import {IonButtons,IonBackButton, IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';
 
</script>