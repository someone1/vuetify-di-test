<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank">
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
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
import HelloWorld from "./components/HelloWorld";
import { VList } from "vuetify/lib";

export default {
  name: "App",
  components: {
    HelloWorld,
    VList
  },
  data() {
    return {
      items: ["one", "two", "three"]
    };
  }
};
</script>
