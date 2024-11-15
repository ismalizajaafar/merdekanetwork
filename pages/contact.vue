<!-- pages/contact.vue -->
<template>
  <div class="overlay">
  <div class="uk-section uk-section-muted">
    <div class="uk-container uk-text-center">
      <div class="uk-margin-large">
        <h2 class="uk-heading-medium uk-scrollspy" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">Contact Us</h2>
        <p class="uk-text-lead uk-scrollspy" uk-scrollspy="cls: uk-animation-fade; delay: 200; repeat: true">
          We would love to hear from you! 
          Reach out to us via the form below.
        </p>
      </div>

      <form class="uk-form-stacked">
        <div class="uk-margin">
          <label class="uk-form-label" for="name">Name</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="name" type="text" placeholder="Your Name" required>
          </div>
        </div>

        <div class="uk-margin">
          <label class="uk-form-label" for="email">Email</label>
          <div class="uk-form-controls">
            <input class="uk-input" id="email" type="email" placeholder="Your Email" required>
          </div>
        </div>

        <div class="uk-margin">
          <label class="uk-form-label" for="message">Message</label>
          <div class="uk-form-controls">
            <textarea class="uk-textarea" id="message" rows="5" placeholder="Your Message" required></textarea>
          </div>
        </div>

        <div class="uk-margin">
          <button class="uk-button uk-button-primary" type="submit">Send Message</button>
        </div>
      </form>
    </div>
  </div>
  </div>
  
</template>

<script setup>
// No additional setup needed
</script>

<style scoped>
.overlay{
  
  background-image: url("@/assets/backg1.jpeg");
  background-size: cover;
}

.uk-heading-medium {
  padding-top: 100px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #1976D2; /* Heading color */
}

.uk-heading-medium {
  padding-top: 100px;
  color: #1976D2; /* Heading color */
}
.uk-button {
  background-color: #B76E3B; /* Consistent button color */
  color: #FFFFF0; /* Button text color */
}
.uk-button:hover {
  background-color: #A95D30; /* Darker shade on hover */
}
</style>
