<template>
  <div class="background">
    <!-- Main Section with About Us Heading and Intro Text -->
    <div class="uk-section uk-section-muted uk-overlay">
      <div class="uk-container uk-text-center uk-margin-large">
        <!-- Keep the "About Us" heading and text with the same effect -->
        <h2 class="uk-heading-medium">About Us</h2>
        <p class="about-us">Learn more about our mission, vision, and values at Merdeka Network.</p>

        <!-- Mission Card -->
        <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 300">
          <h3 class="uk-card-title">Mission</h3>
          <p>To become a leading force in Malaysia’s engineering and telecommunications sectors, recognized for its commitment to quality, innovation, and customer satisfaction. We aim to contribute to sustainable community development and consistently set new standards of excellence across all business endeavors.</p>
        </div>

        <!-- Vision Card -->
        <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 400">
          <h3 class="uk-card-title">Vision</h3>
          <p>To deliver innovative engineering solutions, reliable telecommunication services, and high-quality goods that exceed client expectations and meet diverse market needs. We aim to foster long-term partnerships through exceptional value and customer-focused service.</p>
        </div>

        <!-- Values Card -->
        <div class="uk-card uk-card-default uk-card-body uk-margin-medium" uk-scrollspy="cls: uk-animation-fade; delay: 500">
          <h3 class="uk-card-title">Our Values</h3>
          <p>Integrity, innovation, and commitment to quality in all our endeavors.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// No additional setup needed
</script>

<style scoped>
.background {
  background-image: url("@/assets/backg1.jpeg");
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  min-height: 100vh;
}

.uk-section.uk-overlay {
  background-color: rgba(255, 255, 255, 0.3); /* Light transparent overlay */
  padding: 100px 0; /* Additional padding for top spacing */
}

.uk-heading-medium {
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #1976D2; /* Heading color */
}

.uk-card {
  background-color: rgba(255, 255, 255, 0.95); /* Card background with light transparency */
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.5); /* Card*/
   border-radius: 10px; /*Card border radius */

}

.uk-accordion-title {
  font-size: 1.2rem;
  font-weight: bold;
  color: #333;
  transition: color 0.3s;
}

.uk-accordion-title:hover {
  color: #B76E3B;
}

.uk-accordion-content {
  background-color: #f9f9f9;
}
</style>
