<template>
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
    <v-btn
      v-show="cfab"
      fab
      color="grey darken-4"
      fixed
      right
      bottom
      @click="toContact"
    >
      <v-icon color="white">mdi-email</v-icon>
    </v-btn>
  </v-col>
</template>

<script>
export default {
  name: "FixedBtns",
  components: {},
  data: () => ({
    fab: false,
    cfab: true
  }),

  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 20;
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
    toContact() {
      this.$vuetify.goTo(document.querySelector("#contactRef"));
    }
  }
};
</script>
