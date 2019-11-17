<template>
  <v-navigation-drawer fixed app v-model="drawer">
    <v-list>
      <v-list-item-group v-for="source in sources" :key="source.id">
        <v-list-item>{{ source.name}}</v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import axios from "axios";
export default {
  name: "SideNav",
  props: {
    drawer: Boolean,
    api_key: String
  },
  data: () => ({
    sources: [],
    errors: []
  }),
  methods: {
    selectSource: source => {
      this.$emit("sourceSelected", source);
    }
  },
  created() {
    axios
      .get("https://newsapi.org/v2/sources?language=en&apiKey=" + this.api_key)
      .then(response => {
        this.sources = response.data.sources;
        console.log(response.data.sources);
      });
  }
};
</script>
