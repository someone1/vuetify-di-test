<template>
  <v-app>
    <v-content>
      <v-data-iterator :items="items" content-tag="v-list" content-class="pt-0">
        <template slot="item" slot-scope="props">
          <v-divider key="top-divider" v-if="props.index === 0"></v-divider>
          <v-list-tile :key="props.item">
            <v-list-tile-content>
              <v-list-tile-title class="pr-1">{{ props.item }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-divider :key="props.index"></v-divider>
        </template>
      </v-data-iterator>
    </v-content>
  </v-app>
</template>

<script>
import { VList } from "vuetify/lib";

export default {
  name: "App",
  components: {
    VList
  },
  data() {
    return {
      items: ["one", "two", "three"]
    };
  }
};
</script>
