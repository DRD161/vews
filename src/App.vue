<template>
  <v-app>
    <v-app-bar app color="blue darken-2" class="white--text">
      <v-app-bar-nav-icon @click="drawer = !drawer" color="white"></v-app-bar-nav-icon>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vews</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank">
        <span class="mr-2 white--text">News + Vue = Vews!</span>
      </v-btn>
    </v-app-bar>
    <SideNav :drawer="drawer" :api_key="api_key" @sourceSelected="setSource" />
    <v-content>
      <Card :articles="articles" />
    </v-content>
  </v-app>
</template>

<script>
import axios from "axios";
import SideNav from "./components/SideNav";
import Card from "./components/Card";
export default {
  name: "App",
  components: {
    SideNav,
    Card
  },
  data: () => ({
    drawer: false,
    api_key: "994f086feb9146ccaf706f3a9eca13ec",
    articles: [],
    errors: []
  }),
  methods: {
    setSource(source) {
      axios
        .get("https://newsapi.org/v2/sources" + source + "apiKey=api_key")
        .then(response => {
          this.articles = response.data.articles;
        })
        .catch(e => {
          this.errors.push(e);
        });
    }
  },
  created() {
    axios
      .get(
        "https://newsapi.org/v2/top-headlines?country=us&apiKey=" + this.api_key
      )
      .then(response => {
        this.articles = response.data.articles;
        // console.log(response.data.articles);
      })
      .catch(error => {
        this.errors.push(error);
      });
  }
};
</script>
