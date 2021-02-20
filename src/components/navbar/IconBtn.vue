<template>
  <v-btn
    :href="link"
    target="_blank"
    color="transparent"
    min-width="0"
    width="40px"
    class="elevation-0 p-0"
    rounded
  >
    <v-icon>mdi-{{ icon }}</v-icon>
  </v-btn>
</template>

<script>
export default {
  name: "IconBtn",
  props: {
    icon: String,
    text: String,
    link: String
  },
  data: () => ({})
};
</script>
