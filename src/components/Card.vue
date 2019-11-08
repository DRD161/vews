<template>
  <v-container>
    <v-layout align-center>
      <v-flex xs12 md6 offset-md3>
        <v-card class="mx-auto my-5 pb-3">
          <v-img src="@/assets/400x400.png" height="400px"></v-img>
          <v-card-title>This is the card title. Pull this in via API data!</v-card-title>
          <v-card-text>This is a short desciption.</v-card-text>
          <v-card-actions>
            <v-chip color="secondary">Source</v-chip>
            <v-spacer></v-spacer>
            <v-btn class="mr-2" icon :elevation="2">
              <v-icon class="blue--text text--darken-1">mdi-linkedin</v-icon>
            </v-btn>
            <v-btn class="mr-2" icon :elevation="2">
              <v-icon class="red--text">mdi-reddit</v-icon>
            </v-btn>
            <v-btn class="mr-2" icon :elevation="2">
              <v-icon class="blue--text text--darken-2">mdi-facebook</v-icon>
            </v-btn>
            <v-btn class="mr-2" icon :elevation="2">
              <v-icon class="light-blue--text">mdi-twitter</v-icon>
            </v-btn>
            <v-spacer></v-spacer>
            <v-btn color="primary">Read More</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Card"
};
</script>
