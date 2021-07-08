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
          fill="#212121"
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
          fill="#212121"
          fill-opacity="1"
          d="M0,288L120,240C240,192,480,96,720,58.7C960,21,1200,43,1320,53.3L1440,64L1440,0L1320,0C1200,0,960,0,720,0C480,0,240,0,120,0L0,0Z"
        ></path>
      </svg>
    </div>

    <v-main>
      <FixedBtns />
      <Introduction />
      <instagram-embed
        :url="'https://www.instagram.com/p/CLP6_XBltxB/'"
        :max-width="500"
      />
      <Actions />
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>
      <p>sdsd</p>
      <div style="position: relative">
        <div style="position: relative;z-index: 1">
          <Contact />
        </div>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 1440 700"
          style="position: absolute; top: 0; left: 0;"
        >
          <path
            fill="#212121"
            fill-opacity="1"
            d="M0,160L80,138.7C160,117,320,75,480,85.3C640,96,800,160,960,192C1120,224,1280,224,1360,224L1440,224L1440,320L1360,320C1280,320,1120,320,960,320C800,320,640,320,480,320C320,320,160,320,80,320L0,320Z"
          ></path>

          <rect height="500" width="1449" y="319" fill="#212121" />
        </svg>
      </div>

      <!--<router-view></router-view>-->
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "@/components/navbar/NavBar.vue";
import FixedBtns from "@/components/FixedBtns.vue";
import Introduction from "@/components/Introduction.vue";
import Contact from "@/components/Contact.vue";
import Actions from "@/components/Actions.vue";
import InstagramEmbed from "vue-instagram-embed";

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
    Introduction,
    Contact,
    Actions,
    InstagramEmbed
  }
};
</script>
