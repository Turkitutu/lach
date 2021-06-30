<template>
  <div class="text-center">
    <v-menu
      v-model="menu"
      :close-on-content-click="false"
      :nudge-width="200"
      offset-y
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          v-bind="attrs"
          v-on="on"
          class="elevation-0"
          color="transparent"
          rounded
        >
          <v-icon class="mr-1">mdi-account-multiple-plus</v-icon>
          <span>Join Us</span>
        </v-btn>
      </template>

      <v-card>
        <v-card-actions>
          <span>Sorry, The application is closed currently. Stay tuned!</span>
        </v-card-actions>
      </v-card>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "JoinUs",
  data: () => ({
    fav: true,
    menu: false,
    message: false,
    hints: true
  }),
  methods: {
    openForm() {
      window.open(
        "https://docs.google.com/forms/d/e/1FAIpQLScPk5VUfRtJ8Z3ZNIV_KsogHUb57zOBgUJpSPehoEdf86X6xg/viewform",
        "",
        "width=1000,height=800, ,toolbar=no"
      );
    }
  }
};
</script>
