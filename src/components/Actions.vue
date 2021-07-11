<template>
  <div>
    <h1 class="text-center pa-5">
      Our events
      <v-avatar>
        <img src="../assets/emoji/hand.png" width="30px" />
      </v-avatar>
    </h1>
    <v-sheet class="mx-auto" max-width="1500">
      <v-slide-group
        v-model="model"
        center-active
        show-arrows
        prev-icon="mdi-chevron-left-circle"
        next-icon="mdi-chevron-right-circle"
      >
        <v-slide-item v-for="action in list" :key="action.title">
          <v-card
            class="ma-3 justify-center"
            width="250"
            min-height="350"
            @click.stop="
              act = action;
              dialog = true;
            "
          >
            <v-img
              class="white--text align-end"
              height="200px"
              :src="action.src"
            >
              <v-card-title style="text-shadow: #000 1px 0 10px;">{{
                action.title
              }}</v-card-title>
            </v-img>

            <v-card-subtitle class="pb-0">
              {{ action.date }}
            </v-card-subtitle>

            <v-card-text class="text--primary">
              <div>{{ action.description }}</div>
            </v-card-text>
            <v-row class="fill-height" align="center" justify="center">
              <v-scale-transition>
                <v-icon
                  v-if="active"
                  color="white"
                  size="100"
                  v-text="'mdi-close-circle-outline'"
                ></v-icon>
              </v-scale-transition>
            </v-row>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
    <v-dialog v-model="dialog" max-width="290">
      <v-card>
        <v-card-title class="text-h5">
          {{ act.title }}
        </v-card-title>

        <v-card-text>
          Sorry, this isn't available yet
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn color="green darken-1" text @click="dialog = false">
            Close
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "Actions",
  data: () => ({
    dialog: false,
    act: {},
    list: [
      {
        title: "Valentine's day 2021",
        date: "DECEMBER 28, 2020",
        description: "dddddddddddddddddddddddd",
        src: require("../assets/actions/love2_2021.png")
      },
      {
        title: "Draw a smile",
        date: "DECEMBER 28, 2020",
        description: "dddddddddddddddddddddddd",
        src: require("../assets/actions/draw_a_smile.jpg")
      },
      {
        title: "Beach clean up🌊",
        date: "JUNE 15, 2020",
        description: "dddddddddddddddddddddddd",
        src: require("../assets/actions/clean.png")
      },
      {
        title: "Covid Aid",
        date: "឵឵MARCH 2020",
        description: "dddddddddddddddddddddddd",
        src: require("../assets/actions/corona3.png")
      },
      {
        title: "Valentine's day",
        date: "FEBRUARY 14, 2020",
        description:
          "description bla bla bla bla bla bla bla bla bla bla bla bal",
        src: require("../assets/actions/love2.png")
      },
      {
        title: "Library",
        date: "JANUARY 14, 2020",
        description:
          "description fdddddddddddddddddddddddddsgfdsgfdshdshsddfsgf dsfgfds gfdsgfds gfdsg dsfg dfg",
        src: require("../assets/actions/library.png")
      }
    ],
    model: null
  }),

  methods: {}
};
</script>
