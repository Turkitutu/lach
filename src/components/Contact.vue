<template>
  <v-container class="spacing-playground pa-6" fluid>
    <v-row>
      <v-col cols="12" sm="12" md="6">
        <v-card
          class="mx-auto rounded-lg justify-center"
          elevation="24"
          max-width="700px"
        >
          <v-card-title>Contact</v-card-title>
          <v-card-subtitle>texttttttttttt</v-card-subtitle>
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
              >
              </v-textarea>

              <v-btn
                :disabled="!valid"
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
          <h1 class="white--text font-weight-regular text-md-center">
            Love and Ambition for a Cool Humanity
          </h1>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Contact",
  data: () => ({
    valid: true,
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
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    }
  }
};
</script>
