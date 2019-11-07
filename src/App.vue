<template>
  <v-app>
    <v-app-bar app color="blue darken-2" class="white--text">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        color="white"
      ></v-app-bar-nav-icon>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vews</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2 white--text">News + Vue = Vews!</span>
      </v-btn>
    </v-app-bar>
    <SideNav :drawer="drawer" />
    <v-content>
      <!-- Card component here -->
      <Card />
    </v-content>
  </v-app>
</template>

<script>
import SideNav from "./components/SideNav";
import Card from "./components/Card";
export default {
  name: "App",
  components: {
    SideNav,
    Card
  },
  data: () => ({
    drawer: false
  })
};
</script>
