<template>
  <v-container fluid>
    <v-layout wrap align-center>
      <v-flex xs12 md6 offset-md3 v-for="article in articles" :key="article.title">
        <v-card
          class="mx-auto my-5 pb-3"
          max-width="800px"
          hover
          data-aos="zoom-in"
          data-aos-easing="ease"
        >
          <v-img :src="article.urlToImage" height="400px"></v-img>
          <v-card-title class="subtitle-1">{{ article.title }}</v-card-title>
          <v-card-text>{{ article.description }}</v-card-text>
          <v-container>
            <v-row class="px-2">
              <v-col :sm="12" :md="6" class="d-flex justify-center justify-md-start">
                <v-chip color="secondary">{{ article.source.name }}</v-chip>
              </v-col>
              <v-col class="d-flex justify-center justify-md-end" :sm="12" :md="6">
                <v-btn color="primary" large :href="article.url">Read More</v-btn>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Card',
  props: {
    articles: {
      name: String,
      type: Array,
      required: true
    }
  }
};
</script>
