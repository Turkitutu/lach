<template>
  <v-container>
    <v-card min-height="200" class="elevation-1">
      <v-card-title>📖 Introduction</v-card-title>
      <v-card-text
        >bla blabla bla bla blabla blabla blabla blabla blabla blabla blabla
        blabla bla</v-card-text
      >
      <v-card-title>🎯 Our goals</v-card-title>
      <v-card-text
        >bla blabla bla bla blabla blabla blabla blabla blabla blabla blabla
        blabla bla</v-card-text
      >
      <v-divider class="p-5"></v-divider>
      <h1 class="text-center pa-5">
        Our office members
        <v-avatar>
          <v-img src="../assets/emoji/writing.png" width="30px"></v-img>
        </v-avatar>
      </h1>
      <v-container class="justify-center">
        <v-row class="justify-center" align="center">
          <v-col
            v-for="member in staff"
            :key="member.name"
            align="center"
            md="2"
            sm="4"
            ><v-card
              class="pa-6 rounded-lg justify-center"
              width="200px"
              height="200px"
            >
              <v-avatar size="90" tile class="rounded-circle">
                <img :src="member.avatar" :alt="member.name" />
              </v-avatar>
              <v-chip class="ma-2" color="orange" small outlined>
                {{ member.role }}
              </v-chip>
              <p class="pa-0 ma-0">{{ member.name }}</p>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "Introduction",
  components: {},
  data: () => ({
    staff: [
      {
        name: "Israa Ferjani",
        role: "The president",
        avatar: require("../assets/avatars/israa.png")
      },
      {
        name: "Mohamed Amin Zini",
        role: "Vice president",
        avatar: require("../assets/avatars/zini.png")
      },
      {
        name: "Sarah khedira",
        role: "Chief protocol",
        avatar: require("../assets/avatars/sarra.png")
      },
      {
        name: "Amir Gabsi",
        role: "Chief communication",
        avatar: require("../assets/avatars/amir.png")
      },
      {
        name: "Jawher Ayari",
        role: "Media manager",
        avatar: require("../assets/avatars/jawher.png")
      },
      {
        name: "Chaima Tounsi",
        role: "General secretary",
        avatar: require("../assets/avatars/chaima.png")
      },
      {
        name: "Soltane Slimene",
        role: "Trésorier",
        avatar: require("../assets/avatars/soltane.png")
      },
      {
        name: "Arij Batnini",
        role: "Chief public interest",
        avatar: require("../assets/avatars/arij.png")
      },
      {
        name: "Hamdi Jabnoun",
        role: "Chief sponsorship",
        avatar: require("../assets/avatars/hamdi.png")
      },
      {
        name: "Haithem Turki",
        role: "Assistant Secretary",
        avatar: require("../assets/avatars/haithem.png")
      }
    ]
  }),

  methods: {}
};
</script>
