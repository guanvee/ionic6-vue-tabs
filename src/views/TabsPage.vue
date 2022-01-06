<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button :selected="tabId == 'tab1'" tab="tab1" @click="gogo('tab1')">
          <ion-icon :icon="triangle" />
          <ion-label>Tab 1</ion-label>
        </ion-tab-button>

        <ion-tab-button :selected="tabId == 'tab2'" tab="tab2" @click="gogo('tab2')">
          <ion-icon :icon="ellipse" />
          <ion-label>Tab 2</ion-label>
        </ion-tab-button>

        <ion-tab-button :selected="tabId == 'tab3'" tab="tab3" @click="gogo('tab3')">
          <ion-icon :icon="square" />
          <ion-label>Tab 3</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts" setup>
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage, IonRouterOutlet } from '@ionic/vue';
import { ellipse, square, triangle } from 'ionicons/icons';
import { useIonRouter, createAnimation } from '@ionic/vue';
import { ref } from 'vue';
import { useRoute } from 'vue-router';
const tabId = ref('');
const route=useRoute();
const {id} = route.query;
// tabs 的selected被默认的href设置，所以需要等待一段时间后手动设置tab1≈
setTimeout(() => { tabId.value = 'tab1'; }, 100);
const router = useIonRouter();
const gogo = (tab: string) => {
  tabId.value = tab;
  router.replace(`/tabs/${tab}?id=${id}`, () => createAnimation());
}
</script>