<template>
  <v-app>
    <NavBar />
    <Corousel />
    <FixedBtns />
    <v-main>
      <Introduction />
      <v-divider class="ma-5"></v-divider>
      <Actions />
      <v-divider class="ma-5"></v-divider>
      <Contact />
      <instagram-embed
        :url="'https://www.instagram.com/p/CLP6_XBltxB/'"
        :max-width="500"
      />
      <!--<router-view></router-view>-->
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "@/components/navbar/NavBar.vue";
import FixedBtns from "@/components/FixedBtns.vue";
import Introduction from "@/components/Introduction.vue";
import Contact from "@/components/Contact.vue";
import Actions from "@/components/Actions.vue";
import Corousel from "@/components/Carousel.vue";
import Footer from "@/components/Footer.vue";
import InstagramEmbed from "vue-instagram-embed";

export default {
  name: "App",

  data: () => ({}),
  components: {
    NavBar,
    FixedBtns,
    Introduction,
    Contact,
    Actions,
    Corousel,
    Footer,
    InstagramEmbed
  }
};
</script>
