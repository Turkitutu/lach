<template>
  <v-app>
    <NavBar />

    <div style="position: relative">
      <v-carousel
        height="auto"
        hide-delimiter-background
        show-arrows-on-hover
        dark
      >
        <v-carousel-item v-for="(image, i) in images" :key="i">
          <img :src="image" :alt="image" width="100%" />
        </v-carousel-item>
      </v-carousel>
      <div class="text-center text-no-wrap">
        <v-row justify="center">
          <v-col md="auto" style="position: absolute; bottom:20px">
            <v-img src="./assets/banner.png"></v-img>
          </v-col>
        </v-row>
      </div>
    </div>
    <div style="position: relative;">
      <svg
        style="position: absolute; bottom: 2px;"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1440 320"
      >
        <path
          fill="#263238"
          fill-opacity="1"
          d="M0,288L120,293.3C240,299,480,309,720,304C960,299,1200,277,1320,266.7L1440,256L1440,320L1320,320C1200,320,960,320,720,320C480,320,240,320,120,320L0,320Z"
        ></path>
      </svg>
      <svg
        style="position: absolute; top: -2px;"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1440 320"
      >
        <path
          fill="#263238"
          fill-opacity="1"
          d="M0,288L120,240C240,192,480,96,720,58.7C960,21,1200,43,1320,53.3L1440,64L1440,0L1320,0C1200,0,960,0,720,0C480,0,240,0,120,0L0,0Z"
        ></path>
      </svg>
    </div>
    <v-main>
      <FixedBtns />
      <Introduction />
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>

      <!--<router-view></router-view>-->
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "@/components/navbar/NavBar.vue";
import FixedBtns from "@/components/FixedBtns.vue";
import Introduction from "@/components/Introduction.vue";

export default {
  name: "App",

  data: () => ({
    images: [
      // 1380,700 px
      require("./assets/covers/1.jpg.png"),
      require("./assets/covers/2.jpg.png"),
      require("./assets/covers/3.jpg.png"),
      require("./assets/covers/4.jpg.png")
    ]
  }),
  components: {
    NavBar,
    FixedBtns,
    Introduction
  }
};
</script>
-->
