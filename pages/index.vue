<!-- pages/index.vue -->
<template>
  <div>
    <!-- Parallax Background Section -->
    <div class="home-background">
      <div class="overlay">
        <div class="content">
          <h2 class="uk-heading-large">Welcome to Merdeka Network</h2>
          <p class="uk-text-lead">Explore our innovative solutions in engineering and telecommunications.</p>
          <NuxtLink to="/about" class="uk-button uk-button-primary uk-button-large">Learn More</NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// No additional setup needed
</script>

<style scoped>
/* Remove body and html default margins and padding */
html, body {
  margin: 0;
  padding: 0;
  height: 100%; /* Full height of viewport */
}

/* Parallax Section */
.home-background {
  background-image: url('@/assets/bkg.png');
  background-attachment: fixed; /* Enable parallax effect */
  background-size: cover;
  background-position: center;
  height: 100vh; /* Full height of the viewport */
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  margin: 0; /* Remove default margin */
}

/* Overlay for readability */
.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.6); /* Dark overlay for text visibility */
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Content Styles */
.content {
  text-align: center;
  color: #FFFFF0; /* Text color for visibility */
}

.uk-heading-large {
  color: #B76E3B; /* Copper color for the heading */
  margin-bottom: 1rem; /* Space between heading and paragraph */
}

.uk-text-lead {
  color: #FFFFF0; /* Text color for paragraph */
  margin-bottom: 1.5rem; /* Space below the paragraph */
}

/* Button Styles */
.uk-button-primary {
  background-color: #B76E3B; /* Primary button color */
  border-color: #B76E3B; /* Border color */
}

.uk-button-primary:hover {
  background-color: #A95D30; /* Darker shade on hover */
}

.uk-button-secondary {
  background-color: #1976D2; /* Secondary button color */
  border-color: #1976D2; /* Border color */
}

.uk-button-secondary:hover {
  background-color: #145A9E; /* Darker shade on hover */
}
</style>
