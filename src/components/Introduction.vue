<template>
  <v-col class="mb-4">
    <div class="hidden-sm-and-down">
      <v-timeline>
        <v-timeline-item
          v-for="(item, index) of texts"
          :key="index"
          :color="item.color"
          small
        >
          <v-card class="elevation-2">
            <v-card-title class="text-h5">
              {{ item.title }}
            </v-card-title>
            <v-card-text>
              {{ item.text }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </div>
    <div class="hidden-md-and-up">
      <v-timeline dense>
        <v-timeline-item
          v-for="(item, index) of texts"
          :key="index"
          :color="item.color"
          small
        >
          <v-card class="elevation-2">
            <v-card-title class="text-h5">
              {{ item.title }}
            </v-card-title>
            <v-card-text>
              {{ item.text }}
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </div>
  </v-col>
</template>

<script>
export default {
  name: "Introduction",
  components: {},
  data: () => ({
    texts: [
      {
        title: "Introduction",
        text: "hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh",
        color: "cyan"
      },
      {
        title: "Our goals",
        text: "hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh",
        color: "green"
      },
      {
        title: "idk",
        text: "hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh",
        color: "amber"
      }
    ]
  }),

  methods: {}
};
</script>
