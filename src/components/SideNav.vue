<template>
  <v-navigation-drawer fixed app v-model="drawer">
    <v-list dense class="pt-3 white--text">
      <v-list-item v-for="source in sources" :key="source.id" @click="selectSource(source.id)">
        <v-list-item-action>
          <v-avatar size="32px">
            <img class="img-circle elevation-7 mb-1" :src="getImgUrl(source.id)" />
          </v-avatar>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title @click="closeDrawer()">{{ source.name }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import axios from 'axios';
export default {
  name: 'SideNav',
  props: {
    drawer: Boolean,
    api_key: String
  },
  data: () => ({
    sources: [],
    errors: []
  }),
  methods: {
    getImgUrl(pic) {
      return require('../assets/images/' + pic + '.png');
    },
    selectSource(source) {
      this.$emit('sourceSelected', source);
    },
    closeDrawer() {
      this.$emit('sourceClicked', this.drawer);
    }
  },
  created() {
    axios
      .get('https://newsapi.org/v2/sources?language=en&apiKey=' + this.api_key)
      .then(response => {
        this.sources = response.data.sources;
      });
  }
};
</script>
