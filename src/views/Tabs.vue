<template>
  <ion-page>
    <ion-tabs>
      <ion-tab-bar slot="bottom">
        <ion-tab-button
          :tab="tab.slug"
          :href="`/tabs/${tab.slug}`"
          v-for="tab in tabs"
          :key="tab.slug"
        >
          <ion-icon :icon="tab.icon" />
          <ion-label>{{ tab.label }}</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts">
import {
  IonTabBar,
  IonTabButton,
  IonTabs,
  IonLabel,
  IonIcon,
  IonPage,
} from "@ionic/vue";
import { ellipse, square, triangle } from "ionicons/icons";
import { ref } from "vue";

export default {
  name: "Tabs",
  components: { IonLabel, IonTabs, IonTabBar, IonTabButton, IonIcon, IonPage },
  setup() {
    const tabs = ref([
      {
        icon: triangle,
        slug: "tab1",
        label: "Tab 1",
      },
      {
        icon: ellipse,
        slug: "tab2",
        label: "Tab 2",
      },
      {
        icon: square,
        slug: "tab3",
        label: "Tab 3",
      },
    ]);
    return {
      tabs,
    };
  },
};
</script>
