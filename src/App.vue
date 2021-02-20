<template>
  <v-app>
    <NavBar />

    <v-img class="px-0 pt-0" src="./assets/test.png">
      <v-container>
        <v-row class="mb-6 my-15" justify="center">
          <v-col md="auto">
            <v-img src="./assets/banner.png"></v-img>
          </v-col>
        </v-row>
      </v-container>
    </v-img>
    <v-main>
      <FixedBtns />
      <!--<router-view></router-view>-->
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "@/components/navbar/NavBar.vue";
import FixedBtns from "@/components/FixedBtns.vue";

export default {
  name: "App",

  components: {
    NavBar,
    FixedBtns
  }
};
</script>
-->
