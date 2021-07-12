<template>
  <v-footer dark padless>
    <v-card
      flat
      tile
      class="blue-grey darken-4 white--text text-center"
      width="100%"
      height="220px"
    >
      <v-card-text>
        <v-btn
          v-for="(icon, index) in icons"
          :key="index"
          class="mx-4 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <v-icon size="24px">
            {{ icon.icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Follow us today on our social media <u>#lach.club</u>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        <strong>{{ new Date().getFullYear() }} Copyright</strong> – All Rights
        Reserved to
        <strong>lach club Hammamet</strong>
        <p>
          Website created and designed by <strong>lach club Hammamet</strong>
        </p>
      </v-card-text>
    </v-card>
  </v-footer></template
>

<script>
export default {
  name: "Footer",
  components: {},
  data: () => ({
    icons: [
      { icon: "mdi-facebook", link: "https://www.facebook.com/Lach.club2" },
      { icon: "mdi-instagram", link: "https://www.instagram.com/lach.club/" },
      { icon: "mdi-twitter", link: "" },
      { icon: "mdi-discord", link: "" }
    ]
  })
};
</script>
