<template>
  <v-container fluid class="contact-page">
    <!-- Hero Section -->
    <v-row class="hero-section" justify="center" align="center">
      <v-col cols="12" md="8" class="text-center">
        <h1 class="display-1 title font-weight-bold">Get in Touch</h1>
        <p class="text-h6 mt-4 title">
          We’re here to help you with any questions or inquiries.
        </p>
      </v-col>
    </v-row>

    <!-- Contact Section -->
    <v-row class="contact-options mt-10" justify="center" align="flex-start">
      <!-- Feedback Form on the Left -->
      <v-col cols="12" md="6">
        <v-card elevation="2" class="pa-6">
          <h2 class="text-h4 font-weight-bold mb-4">Contact Us</h2>
          <p class="text-body-1 mb-6">
            Fill out the form below, and we’ll get back to you as soon as possible.
          </p>
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

      <!-- Contact Options (Email Us & Visit Us) on the Right -->
      <v-col cols="12" md="6">
  <v-row dense class="contact-cards">
    <!-- Email Us Card -->
    <v-col cols="12">
      <v-card class="text-center contact-card card-spacing" elevation="3">
        <v-icon color="primary" size="48" class="mt-4">mdi-email</v-icon>
        <v-card-title class="headline font-weight-bold mt-2">Email Us</v-card-title>
        <v-card-text>Reach out to us via email for any inquiries.</v-card-text>
        <v-card-text>support@merdekanetwork.com</v-card-text>
      </v-card>
    </v-col>

    <!-- Space Between Cards -->
    <v-col cols="12" class="mt-4"></v-col>

    <!-- Visit Us Card -->
    <v-col cols="12">
      <v-card class="text-center contact-card card-spacing" elevation="3">
        <v-icon color="primary" size="48" class="mt-4">mdi-map-marker</v-icon>
        <v-card-title class="headline font-weight-bold mt-2">Visit Us</v-card-title>
        <v-card-text>Find our office and meet us in person.</v-card-text>
        <v-card-text>
          <a href="https://maps.app.goo.gl/ABiRKRisf7tB5ZDV8">Lot A-1-11 Pusat Komersial Jalan Kuching Jalan Kepayang,
           Off, Jln Kuching, 51200 Kuala Lumpur,
            Federal Territory of Kuala Lumpur, Malaysia</a>
          <br />
          <p>Phone: +60 3-62424474</p>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
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
        email: (value) => /.+@.+\..+/.test(value) || "E-mail must be valid.",
      },
      contactOptions: [
        {
          icon: "mdi-email",
          title: "Email Us",
          description: "Reach out to us via email for any inquiries.",
          email: "support@merdekanetwork.com", // Display the email directly
        },
        {
          icon: "mdi-map-marker",
title: "Visit Us",
description: "Find our office and meet us in person.",
address: '<a href="https://g.co/kgs/Nja73j4" target="_blank">Lot A-1-11 Pusat Komersial Jalan Kuching Jalan Kepayang Off Jln Kuching 51200 Kuala Lumpur Federal Territory of Kuala Lumpur</a>', // Your office address as a hyperlink

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
  background-repeat: no-repeat;
  background-position: center;
  min-height: 100vh; /* Ensures the container fills the viewport */
  display: flex;
  flex-direction: column;
  justify-content: space-between; /* Ensures content fills vertically with no gaps */
  padding: 40px 0;
  margin: 0; /* Removes extra margin */
}

.title{
  color: #f9f9f9;
}

.card-spacing {
  margin-bottom: 20px; /* Adjust spacing as needed */
}


.hero-section {
  text-align: center;
  margin-bottom: 0;
  margin-top: 100px;
}
.contact-options{
  padding-left: 250px;
  
}
.contact-card{
  margin-bottom: 50px;
}
.contact-options .contact-card {
  padding: 20px;
  min-height: 250px;
  max-width: 400px;
  margin: auto;
  transition: transform 0.3s, box-shadow 0.3s;
}
.contact-options .contact-card:hover {
  transform: translateY(-5px);
  box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.15);
}

.contact-form-section {
  background-color: white;
  padding: 40px;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  padding-right: 100px ;
}

.v-btn {
  text-transform: none;
}

a.text-primary {
  text-decoration: none;
}
</style>