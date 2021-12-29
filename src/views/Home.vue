<template>
    <ion-page>
        <ion-content style="text-align: center;line-height: 400%;">
            <router-link to="/test">test link</router-link>
            <br/>
            <router-link to="/tabs/tab1">tab link</router-link>
            <br/>
        </ion-content>
    </ion-page>
</template>
<script lang="ts" setup>
import { IonPage, IonContent } from '@ionic/vue';
import { RouterLink } from 'vue-router';

</script>
