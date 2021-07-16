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
            <div>
              <v-img
                class="white--text align-end"
                height="200px"
                :src="action.src"
              >
                <v-card-title style="text-shadow: #000 1px 0 10px;">{{
                  action.title
                }}</v-card-title>
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
            </div>

            <v-card-subtitle class="pb-0">
              {{ action.date }}
            </v-card-subtitle>

            <v-card-text class="text--primary" style="font-size:14px">
              <div>{{ action.description }}</div>
            </v-card-text>
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
        description: "Missing description",
        src: require("../assets/actions/love2_2021.png")
      },
      {
        title: "Draw a smile",
        date: "DECEMBER 28, 2020",
        description: "Missing description",
        src: require("../assets/actions/draw_a_smile.png")
      },
      {
        title: "Beach clean up🌊",
        date: "JUNE 15, 2020",
        description: "Missing description",
        src: require("../assets/actions/clean.png")
      },
      {
        title: "Covid Aid",
        date: "឵឵MARCH 2020",
        description:
          "After the beginning of the COVID-19 pandemic, many people have been stuck between two deadly choices, either staying at home without a job to live by, or going out and risking their lives. March 2020 is when we went to some poor neighborhoods to give them somme food so that they can at least stay safe.",
        src: require("../assets/actions/corona3.png")
      },
      {
        title: "Valentine's day",
        date: "FEBRUARY 14, 2020",
        description:
          "It's the valentine's day, so we went to our secondary school and made some ambiance related to the theme of love by giving students some sweet, chocolate, love letters and the chance to freely express their feelings by writing down the names of their lovers on a board as a beautiful memory that will last for them.",
        src: require("../assets/actions/love2.png")
      },
      {
        title: "Library",
        date: "JANUARY 14, 2020",
        description:
          "Aatef Chaieb secondary school in hammamet is where our club started, the first step we wanted to begin with is opening a library so that people can read and revise for their exams in an appropriate place. There was an empty room so we worked hard on it by cleaning, painting, decorating and adding up books and the result was really amazing as you see.",
        src: require("../assets/actions/library.png")
      }
    ],
    model: null
  }),

  methods: {}
};
</script>
