<template>
  <v-container>
    <v-card min-height="200" class="elevation-1 mt-14">
      <v-card-title class="pb-0"
        >Welcome to Love and Ambition for a Cool Humanity (LACH) Club!
      </v-card-title>
      <v-card-title class="pt-2">🔎 Who we are</v-card-title>
      <v-card-text
        >We are a group of teenagers who noticed that there are some negative
        habits and things happening in our environment that need to be reformed,
        and since we strongly believe that the change has to come from within,
        we wanted to do it through this nonprofit club in November 2019.
        Everyone is welcome to be a member of this family ❤</v-card-text
      >
      <v-card-title>🎯 Our goals</v-card-title>
      <v-card-text
        >Our main goal is to give young people the opportunity to develop their
        skills and strengthen their personalities to create a positive
        change.</v-card-text
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
              class="pt-5 rounded-lg justify-center"
              :class="
                'rounded-lg justify-center ' +
                  ($vuetify.breakpoint.xs ? 'pt-0' : 'pt-7')
              "
              :width="$vuetify.breakpoint.xs ? '140px' : '200px'"
              :height="$vuetify.breakpoint.xs ? '140px' : '200px'"
            >
              <v-avatar
                :size="$vuetify.breakpoint.xs ? 60 : 90"
                tile
                class="rounded-circle"
              >
                <v-img :src="member.avatar" :alt="member.name">
                  <template v-slot:placeholder>
                    <v-sheet>
                      <v-skeleton-loader
                        type="image"
                        width="100%"
                        class="mx-auto"
                      ></v-skeleton-loader>
                    </v-sheet>
                  </template>
                </v-img>
              </v-avatar>
              <p
                :style="$vuetify.breakpoint.xs ? 'font-size:14px' : ''"
                class="pa-0 ma-0"
              >
                {{ member.name }}
              </p>
              <v-chip
                v-if="!$vuetify.breakpoint.xs"
                class="ma-2"
                color="orange"
                small
                outlined
              >
                {{ member.role }}
              </v-chip>
              <v-chip
                v-if="$vuetify.breakpoint.xs"
                class="ma-2"
                color="orange"
                x-small
                outlined
              >
                {{ member.role }}
              </v-chip>
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
        role: "President",
        avatar: require("../assets/avatars/israa.png")
      },
      {
        name: "Mohamed Amine Zini",
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
        role: "Treasurer",
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
