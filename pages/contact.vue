<template>
  <v-container fluid class="contact-page">
    <!-- Hero Section -->
    <v-row class="hero-section" justify="center" align="center">
      <v-col cols="12" md="8" class="text-center">
        <h1 class="display-1 font-weight-bold">Get in Touch</h1>
        <p class="text-h6 mt-4">
          Have questions or need assistance? Our team is here to help.
        </p>
      </v-col>
    </v-row>

    <!-- Contact Options -->
    <v-row class="contact-options mt-10" justify="center" align="center">
      <v-col cols="12" md="4" v-for="(option, index) in contactOptions" :key="index">
        <v-card class="text-center" elevation="2">
          <v-icon color="primary" large class="mt-4">{{ option.icon }}</v-icon>
          <v-card-title class="headline font-weight-bold">{{ option.title }}</v-card-title>
          <v-card-text>{{ option.description }}</v-card-text>
          <v-btn :href="option.link" color="primary" class="mt-3">
            {{ option.buttonText }}
          </v-btn>
        </v-card>
      </v-col>
    </v-row>

    <!-- Contact Form Section -->
    <v-row class="contact-form-section mt-10" justify="center">
      <v-col cols="12" md="8">
        <v-card elevation="2" class="pa-6">
          <h2 class="text-h4 font-weight-bold mb-4">Send Us a Message</h2>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-row dense>
              <v-col cols="12" md="6">
                <v-text-field
                  label="Your Name"
                  v-model="form.name"
                  :rules="[rules.required]"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field
                  label="Email Address"
                  v-model="form.email"
                  :rules="[rules.required, rules.email]"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-textarea
              label="Message"
              v-model="form.message"
              :rules="[rules.required]"
              rows="4"
              required
            ></v-textarea>
            <v-btn
              color="primary"
              class="mt-4"
              :disabled="!valid"
              @click="submitForm"
            >
              Send Message
            </v-btn>
          </v-form>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      form: {
        name: "",
        email: "",
        message: "",
      },
      rules: {
        required: (value) => !!value || "This field is required.",
        email: (value) =>
          /.+@.+\..+/.test(value) || "E-mail must be valid.",
      },
      contactOptions: [
        {
          icon: "mdi-email",
          title: "Email Us",
          description: "Get in touch via email for detailed inquiries.",
          buttonText: "Send an Email",
          link: "mailto:info@merdekanetwork.com",
        },
        {
          icon: "mdi-map-marker",
          title: "Visit Us",
          description: "Find our office for in-person assistance.",
          buttonText: "Get Directions",
          link: "https://g.co/kgs/NZm8sWx",
        },
      ],
    };
  },
  methods: {
    submitForm() {
      if (this.$refs.form.validate()) {
        alert("Message sent successfully!");
        // Reset form
        this.form.name = "";
        this.form.email = "";
        this.form.message = "";
        this.$refs.form.reset();
      }
    },
  }, 
};
</script>

<style scoped>
.contact-page {
  background-image: url("@/assets/backg3.jpeg");
  background-size: cover;
}

.display-1{
  color: #f9f9f9;
}

.hero-section {
  /* min-height: 20vh; */
  background: url("/images/contact-hero.jpg") no-repeat center center;
  background-size: cover;
  color: white;
  text-align: center;
  margin-top: 100px;
}

.contact-options .v-card {
  padding: 20px;
  min-height: 300px;
  max-width: 450px;
  margin: auto;
}

.contact-form-section {
  background-color: white;
  padding: 40px 20px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  max-width: 700px;
  margin: auto;
}
</style>
