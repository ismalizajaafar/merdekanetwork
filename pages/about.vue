<template>
  <div class="background">
    <!-- Main Section -->
    <section class="uk-section uk-overlay">
      <div class="uk-container uk-text-center uk-margin-large">
        <!-- "About Us" Heading and Text -->
        <h2 class="uk-heading-medium">About Us</h2>
        <p class="about-us">
          Learn more about our mission, vision, and values at Merdeka Network.
        </p>

        <!-- Mission, Vision, and Values Cards -->
        <div class="uk-grid-match uk-child-width-1-3@m uk-grid-medium" uk-grid>
          <!-- Mission -->
          <div>
            <div class="uk-card uk-card-hover uk-card-default uk-card-body" uk-scrollspy="cls: uk-animation-slide-bottom; delay: 300">
              <span class="uk-icon-button uk-margin-small-bottom" uk-icon="heart"></span>
              <h3 class="uk-card-title">Mission</h3>
              <p>
                To become a leading force in Malaysia’s engineering and telecommunications sectors, recognized for its commitment to quality, innovation, and customer satisfaction. We aim to contribute to sustainable community development and set new standards of excellence.
              </p>
            </div>
          </div>

          <!-- Vision -->
          <div>
            <div class="uk-card uk-card-hover uk-card-default uk-card-body" uk-scrollspy="cls: uk-animation-slide-bottom; delay: 400">
              <span class="uk-icon-button uk-margin-small-bottom" uk-icon="future"></span>
              <h3 class="uk-card-title">Vision</h3>
              <p>
                To deliver innovative engineering solutions, reliable telecommunication services, and high-quality goods that exceed client expectations. We aim to foster long-term partnerships through exceptional value and service.
              </p>
            </div>
          </div>

          <!-- Values -->
          <div>
            <div class="uk-card uk-card-hover uk-card-default uk-card-body" uk-scrollspy="cls: uk-animation-slide-bottom; delay: 500">
              <span class="uk-icon-button uk-margin-small-bottom" uk-icon="star"></span>
              <h3 class="uk-card-title">Our Values</h3>
              <p>Integrity, innovation, and commitment to quality in all our endeavors.</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// No additional setup needed for this UIKit-based design
</script>

<style scoped>
.background {
  background-image: url("@/assets/backg3.jpeg");
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  min-height: 100vh;
}

/* .uk-section.uk-overlay {
  background-color: rgba(255, 255, 255, 0.2); /* Light transparent overlay */
  /* background-size: cover; */
  


.about-us {
  color: #f9fcf8;
  font-weight: bold;
  font-size: 1.2rem;
  margin-bottom: 100px;

}

.uk-heading-medium {
  padding-top: 100px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  color: #f9fcf8;
  -webkit-text-stroke: 1px #333;
}

.uk-card-hover {
  border-radius: 12px;
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
}

.uk-icon-button {
  background-color: #333;
  color: #fff;
  transition: transform 0.3s ease;
}

.uk-icon-button:hover {
  transform: scale(1.2);
  background-color: #b76e3b;
}
</style>
