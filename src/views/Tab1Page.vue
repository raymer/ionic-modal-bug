<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-button @click="openModal">Open Modal</ion-button>

      <ExploreContainer name="Tab 1 page" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, modalController, IonButton } from '@ionic/vue';
import ExploreContainer from '@/components/ExploreContainer.vue';
import TestModal from './test-modal.vue';

async function openModal() {
  const modal = await modalController.create({
    component: TestModal,
  });
  modal.present();

  await modal.onDidDismiss();
}
</script>
