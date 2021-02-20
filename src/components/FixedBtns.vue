<template>
  <!--<div class="text-center">
    <v-btn v-show="true" fab color="grey darken-4" fixed large right bottom>
      <v-icon color="white">mdi-email</v-icon>
    </v-btn>
    <v-btn
      v-scroll="onScroll"
      v-show="fab"
      fab
      dark
      fixed
      bottom
      right
      color="primary"
      @click="toTop"
    >
      <v-icon white large>mdi-chevron-up</v-icon>
    </v-btn>
  </div>-->

  <v-col cols="12" sm="6">
    <v-btn
      v-scroll="onScroll"
      v-show="fab"
      fab
      dark
      fixed
      class="my-15"
      bottom
      right
      color="primary"
      @click="toTop"
    >
      <v-icon white large>mdi-chevron-up</v-icon>
    </v-btn>
    <v-btn v-show="true" fab color="grey darken-4" fixed right bottom>
      <v-icon color="white">mdi-email</v-icon>
    </v-btn>
  </v-col>
</template>

<script>
export default {
  name: "FixedBtns",
  components: {},
  data: () => ({
    fab: false
  }),

  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 20;
    },
    toTop() {
      this.$vuetify.goTo(0);
    }
  }
};
</script>
