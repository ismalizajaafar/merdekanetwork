<!-- pages/about.vue -->
<template>
  <!-- Main Section with About Us Heading and Intro Text -->
<div class="uk-section uk-section-muted">
  <div class="uk-container uk-text-center uk-margin-large">
    <!-- Keep the "About Us" heading and text with the same effect -->
    <h2 class="uk-heading-medium">About Us</h2>
    <p class="about-us">Learn more about our mission, vision, and values at Merdeka Network.</p>

    <!-- Mission Card -->
    <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 300">
      <h3 class="uk-card-title">Our Mission</h3>
      <p>To become a leading force in Malaysia’s engineering and telecommunications sectors, recognized for its commitment to quality, innovation, and customer satisfaction. We aim to contribute to sustainable community development and consistently set new standards of excellence across all business endeavors.</p>
    </div>

    <!-- Vision Card -->
    <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 400">
      <h3 class="uk-card-title">Our Vision</h3>
      <p>To deliver innovative engineering solutions, reliable telecommunication services, and high-quality goods that exceed client expectations and meet diverse market needs. We aim to foster long-term partnerships through exceptional value and customer-focused service.</p>
    </div>

    <!-- Values Card -->
    <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 500">
      <h3 class="uk-card-title">Our Values</h3>
      <p>Integrity, innovation, and commitment to quality in all our endeavors.</p>
    </div>
  </div>
</div>
</template>

<script setup>
// No additional setup needed
</script>

<style scoped>
.uk-section{
  background-image: url("@/assets/backg2.png");
}
.uk-heading-medium {
  padding-top: 100px;
  font-weight: bold;
  color: #1976D2; /* Heading color */
}
.uk-accordion-title {
  font-size: 1.2rem;
  font-weight: bold; /* Consistent font size */
  color: #333; /* Dark gray for title color */
  transition: color 0.3s;
}
.uk-accordion-title:hover {
  color: #B76E3B; /* Hover effect */
}
.uk-accordion-content {
  background-color: #f9f9f9; /* Light background for content */
}
</style>
