<template>
  <v-app-bar style="background : #000000ba" app dark>
    <div class="d-flex align-center">
      <v-img
        alt="lach Logo"
        class="shrink mr-2"
        contain
        src="@/assets/logo_gold.png"
        transition="scale-transition"
        width="50"
      />
      <v-img
        alt="lach name"
        class="shrink mt-1 hidden-sm-and-down"
        contain
        min-width="100"
        src="@/assets/name_large.png"
      />
    </div>
    <v-spacer></v-spacer>

    <JoinUs />
    <IconBtn icon="instagram" link="https://www.instagram.com/lach.club/" />
    <IconBtn icon="facebook" link="https://www.facebook.com/Lach.club2" />
  </v-app-bar>
</template>

<script>
import IconBtn from "@/components/navbar/IconBtn.vue";
import JoinUs from "@/components/navbar/JoinUs.vue";

export default {
  name: "NavBar",
  components: {
    IconBtn,
    JoinUs
  },
  data: () => ({})
};
</script>
