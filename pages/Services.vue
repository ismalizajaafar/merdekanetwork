<template>
  <div>
    <!-- Hero Section -->
    <section class="uk-section uk-section-muted hero-section">
      <div class="uk-container uk-text-center uk-margin-large">
        <div class="hero-overlay" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">
          <h1 class="uk-heading-large hero-title">Our Services</h1>
          <p class="uk-text-lead hero-subtitle" uk-scrollspy="cls: uk-animation-fade; delay: 200; repeat: true">
            Explore our range of services designed to meet your needs with top-notch solutions.
          </p>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <v-container class="services-section" fluid>
      <v-row class="text-center">
        <v-col cols="12" md="4" v-for="(service, index) in services" :key="index">
          <v-card
            class="service-card"
            elevation="10"
            uk-scrollspy="cls: uk-animation-slide-right; delay: 300; repeat: true"
          >
            <v-img :src="service.image" alt="Service Image" height="250px"></v-img>
            <v-card-title class="headline">{{ service.title }}</v-card-title>
            <v-card-text>{{ service.description }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Importing images directly
import pcMaintenanceImage from '@/assets/pcmaintain.jpg'
import serverSetupImage from '@/assets/data.png'
import networkingImage from '@/assets/network.jpg'
import cloudImage from '@/assets/cloud.jpg'

// Defining the services array with imported images
const services = ref([
  { title: "PC Maintenance", image: pcMaintenanceImage, description: "Regular maintenance and support for all PC systems." },
  { title: "Server Setup", image: serverSetupImage, description: "Professional server setup for businesses of all sizes." },
  { title: "Networking Solutions", image: networkingImage, description: "Comprehensive networking solutions for seamless connectivity." },
  { title: "Cloud Storage", image: cloudImage, description: "Secure, scalable cloud storage with top-notch encryption and reliability." },
])
</script>

<style scoped>
/* Hero Section */
.hero-section {
  background-image: url("@/assets/service.jpg");
  background-size: cover;
  background-position: center;
  position: relative;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.hero-overlay {
  background-color: rgba(0, 0, 0, 0.5); /* Dark overlay */
  padding: 30px;
  text-align: center;
}

.hero-title {
  font-size: 3rem;
  font-family: Arial, Helvetica, sans-serif;
  margin: 0;
  text-transform: uppercase;
  color: #fff;
}

.hero-subtitle {
  font-size: 1.25rem;
  font-weight: 300;
  margin-top: 15px;
  color: #fff;
}

/* Services Section */
.services-section {
  padding: 40px 20px;
  background-color: #f9f9f9;
}

.service-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 6px 30px rgba(0, 0, 0, 0.2);
}

.service-card v-card-title {
  font-size: 1.2rem;
  font-weight: bold;
}

.service-card v-card-text {
  color: #555;
}

/* Add padding and more spacing */
.uk-section-muted {
  padding-top: 60px;
  padding-bottom: 60px;
}

.uk-container {
  max-width: 1200px;
  margin: 0 auto;
}
</style>
