<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="primary">
        <ion-title>Home</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content padding>
      <p>kurihara</p>
      <ion-list>
        <ion-item>
          <ion-checkbox slot="start"></ion-checkbox>
          <ion-label>
            <h1>Create Idea</h1>
            <ion-note>Run Idea by Brandy</ion-note>
          </ion-label>
          <ion-badge color="success" slot="end">5 Days</ion-badge>
        </ion-item>
      </ion-list>

      <ion-fab vertical="bottom" horizontal="end" slot="fixed">
        <ion-fab-button @click="takePhoto()">
          <ion-icon name="camera" />
        </ion-fab-button>
      </ion-fab>

    </ion-content>
  </ion-page>
</template>

<script>
import { camera, trash, close } from 'ionicons/icons';

import {
  Plugins,
  CameraSource,
  CameraResultType
} from "@capacitor/core";
const { Camera } = Plugins;

export default {
  name: 'About',
  props: {
    msg: String
  },
  methods: {
    takePhoto: async () => {
      const image = await Camera.getPhoto({
        quality: 90,
        allowEditing: true,
        resultType: CameraResultType.DataUrl,
        source: CameraSource.Prompt
      });
    },
  },
}
</script>
