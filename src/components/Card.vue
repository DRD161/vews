<template>
  <v-container>
    <v-layout wrap align-center>
      <v-flex
        xs12
        md6
        offset-md3
        v-for="article in articles"
        :key="article.title"
      >
        <v-card class="mx-auto my-5 pb-3">
          <v-img :src="article.urlToImage" height="400px"></v-img>
          <v-card-title>{{ article.title }}</v-card-title>
          <v-card-text>{{ article.description }}</v-card-text>
          <v-container>
            <v-row class="px-2">
              <v-col :sm="6" :md="3">
                <v-chip color="secondary" small>{{
                  article.source.name
                }}</v-chip>
              </v-col>
              <v-spacer></v-spacer>
              <v-col class="d-flex justify-center" :sm="6" :md="6">
                <v-btn class="mr-2" icon :elevation="2">
                  <v-icon class="blue--text text--darken-1"
                    >mdi-linkedin</v-icon
                  >
                </v-btn>
                <v-btn class="mr-2" icon :elevation="2">
                  <v-icon class="red--text">mdi-reddit</v-icon>
                </v-btn>
                <v-btn class="mr-2" icon :elevation="2">
                  <v-icon class="blue--text text--darken-2"
                    >mdi-facebook</v-icon
                  >
                </v-btn>
                <v-btn class="mr-2" icon :elevation="2">
                  <v-icon class="light-blue--text">mdi-twitter</v-icon>
                </v-btn>
              </v-col>
              <v-spacer></v-spacer>
              <v-col class="align-self-end" :md="3">
                <v-btn small color="primary">Read More</v-btn>
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
  name: "Card",
  props: {
    articles: {
      name: String,
      type: Array,
      required: true
    }
  }
};
</script>
