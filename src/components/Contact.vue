<template>
  <v-btn v-show="true" fab color="grey darken-4" fixed large bottom right>
    <v-icon color="white">mdi-email</v-icon>
  </v-btn>
</template>

<script>
export default {
  name: "Contact",
  components: {},
  data: () => ({
    fab: true
  })
};
</script>
