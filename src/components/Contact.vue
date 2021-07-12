<template>
  <div style="position: relative" id="contactRef">
    <div style="position: relative;z-index: 1">
      <v-container class="spacing-playground pa-6" fluid>
        <v-row>
          <v-col cols="12" sm="12" md="6">
            <v-card
              class="mx-auto rounded-lg justify-center"
              elevation="24"
              max-width="700px"
              :loading="loading"
            >
              <v-card-title>Contact</v-card-title>
              <v-card-subtitle
                >If you have any questions, just fill in the contact form and we
                will anwser you shortly via email.<br />
                You can also contact us via
                <a href="https://www.facebook.com/Lach.club2/">facebook</a> or
                <a href="https://www.instagram.com/lach.club/">instagram</a>.
              </v-card-subtitle>
              <v-card-text>
                <v-form class="" ref="form" v-model="valid" lazy-validation>
                  <v-text-field
                    v-model="firstname"
                    :counter="10"
                    :rules="fnameRules"
                    label="Frist name"
                    outlined
                    dense
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="lastname"
                    :counter="10"
                    :rules="lnameRules"
                    label="Last name"
                    outlined
                    dense
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                    outlined
                    dense
                  ></v-text-field>

                  <v-text-field
                    :counter="30"
                    v-model="subject"
                    :rules="subjectRules"
                    label="Subject"
                    required
                    outlined
                    dense
                  ></v-text-field>

                  <v-textarea
                    :counter="350"
                    outlined
                    dense
                    v-model="message"
                    :rules="messageRules"
                    label="Message"
                    :rows="$vuetify.breakpoint.xs ? 2 : 4"
                  >
                  </v-textarea>

                  <v-btn
                    :disabled="!valid || loading"
                    :loading="loading"
                    color="success"
                    class="mr-4"
                    @click="validate"
                  >
                    Submit
                  </v-btn>

                  <v-btn color="error" class="mr-4" @click="reset">
                    Reset
                  </v-btn>
                </v-form>
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" sm="12" md="6">
            <div class="text-xs-center">
              <v-img
                class="mx-auto"
                src="../assets/logo_gold.png"
                width="400px"
              ></v-img>
              <h1 class="white--text font-weight-regular text-center">
                Love and Ambition for a Cool Humanity
              </h1>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 550"
      style="position: absolute; top: 0; left: 0;"
    >
      <path
        fill="#212121"
        fill-opacity="1"
        d="M0,160L80,138.7C160,117,320,75,480,85.3C640,96,800,160,960,192C1120,224,1280,224,1360,224L1440,224L1440,320L1360,320C1280,320,1120,320,960,320C800,320,640,320,480,320C320,320,160,320,80,320L0,320Z"
      ></path>
    </svg>
    <v-card
      style="position: absolute; top: 20vw; left: 0;"
      color="#212121"
      width="100%"
      :height="cardHeight"
      class="elevation-0 rounded-0"
    ></v-card>
    <v-snackbar v-model="snackbar" :timeout="20000">
      {{ snackbarMessage }}

      <template v-slot:action="{ attrs }">
        <v-btn color="blue" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>

<script>
export default {
  name: "Contact",
  cardHeight: "350px",

  data: () => ({
    loading: false,
    valid: true,
    snackbar: false,
    snackbarMessage: "",
    firstname: "",
    fnameRules: [
      v => !!v || "First name is required",
      v => (v && v.length <= 10) || "First name must be less than 10 characters"
    ],
    lastname: "",
    lnameRules: [
      v => !!v || "Last name is required",
      v => (v && v.length <= 10) || "Last name must be less than 10 characters"
    ],
    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    subject: "",
    subjectRules: [
      v => !!v || "Subject is required",
      v => (v && v.length <= 30) || "Subject must be less than 30 characters"
    ],
    message: "",
    messageRules: [
      v => !!v || "Message is required",
      v => (v && v.length <= 350) || "Message must be less than 350 characters"
    ]
  }),
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.loading = true;
        setTimeout(() => {
          this.axios
            .post("./message", {
              firstName: this.firstname,
              lastName: this.lastname,
              email: this.email,
              subject: this.subject,
              message: this.message
            })
            .then(response => {
              if (response.data.result == "error") {
                this.snackbarMessage = "Something is wrong, try again!";
              } else {
                this.snackbarMessage =
                  "Your message has been sent successfully, we will reply to you as soon as possible, Thank you!";
                this.$refs.form.reset();
              }
              this.snackbar = true;
              this.loading = false;
            })
            .catch(error => {
              console.log(error);
              this.snackbarMessage = "Something is wrong, try again!";
              this.snackbar = true;
              this.loading = false;
            });
        }, 1000);
      }
    },
    reset() {
      this.$refs.form.reset();
    },
    submit() {}
  },
  computed: {
    // eslint-disable-next-line vue/return-in-computed-property
    cardHeight() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "1200px";
        case "sm":
          return "1200px";
        case "md":
          return "1200px";
        case "lg":
          return "400px";
        case "xl":
          return "400px";
      }
    }
  }
};
</script>
