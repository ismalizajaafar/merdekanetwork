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
  background-image: url('@/assets/backg3.jpeg');
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
  background-color: rgb(245, 238, 238,0); /* Dark overlay for text visibility */
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Content Styles */
.content {
  text-align: center;
  color: #3333; /* Text color for visibility */
}

.uk-heading-large {
  color: #F9FCF8; /* Copper color for the heading */
  font-weight: 950;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  /* font-stretch: wider; */
  margin-bottom: 1rem;
  
  /* Outline effect */
  -webkit-text-stroke: 1px #fff; /* Black outline */
  
  /* Shadow effect for a bubble look */
  text-shadow: 4px 4px 5px rgba(0, 0, 0, 0.9),
               0px 0px 15px rgba(255, 215, 255, 0.6);

  /* Additional styling to make it more bubble-like */
  font-size: 5rem; /* Adjust font size as needed */
  padding: 5px;
}


.uk-text-lead {
  color: #F9FCF8; /* Text color for paragraph */
  font-weight: bold;
  margin-bottom: 1.5rem; /* Space below the paragraph */

  -webkit-text-stroke: 0px #fff;
  /* text-shadow: 4px 4px 7px rgb(255, 255, 255),
               0px 0px 7px rgb(255, 255, 255); */
}

/* Button Styles */
.uk-button-primary {
  background-color: #743843; /* Primary button color */
  border-color: #743843; /* Border color */
  color: #F9FCF8; /* White text for contrast */
  font-weight: bold;
  
  /* Shadow for depth */
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2), /* Basic shadow */
              0px 0px 10px rgb(255, 255, 255); /* Orange glow */

  /* Transition for hover effect */
  transition: box-shadow 0.3s ease;
}

/* Additional hover effect to enhance glow */
.uk-button-primary:hover {
  box-shadow: 0px 6px 8px rgba(0, 0, 0, 0.3), /* Slightly deeper shadow */
              0px 0px 15px rgba(168, 73, 105, 0.8); /* Stronger glow */
}


.uk-button-primary:hover {
  background-color: #d8aab3; /* Darker shade on hover */
}

.uk-button-secondary {
  background-color: #1976D2; /* Secondary button color */
  border-color: #1976D2; /* Border color */
}

.uk-button-secondary:hover {
  background-color: #145A9E; /* Darker shade on hover */
}
</style>
