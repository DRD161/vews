<template>
  <v-navigation-drawer fixed app clipped v-model="drawer">
    <p>test</p>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "SideNav",
  props: ["drawer"]
};
</script>
