<template>
  <div class="page-background">
    <div class="background">
      <!-- Service Overview -->
      <div class="uk-section uk-section-muted overview" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">
        <div class="uk-container uk-text-center">
          <h1 class="uk-heading-medium">Our Network Services</h1>
          <p class="uk-text-lead">
            At Merdeka Network, we specialize in providing robust and reliable network solutions tailored to meet the
            demands of modern businesses. Our services include network design, setup, monitoring, and support for
            enterprises of all sizes.
          </p>
        </div>
      </div>

      <!-- Core Features -->
      <div class="uk-section uk-section-default features" uk-scrollspy="cls: uk-animation-slide-left; delay: 200; repeat: true">
        <div class="uk-container">
          <h2 class="uk-heading-medium">Core Features</h2>
          <div class="uk-grid-small uk-child-width-1-2@m uk-flex-center" uk-grid>
            <div v-for="(feature, index) in features" :key="index" class="feature-item">
              <div class="uk-card uk-card-default uk-card-body">
                <h3 class="uk-card-title">{{ feature.title }}</h3>
                <p>{{ feature.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Customer Testimonials -->
      <div class="uk-section uk-section-muted testimonials" uk-scrollspy="cls: uk-animation-slide-right; delay: 400; repeat: true">
        <div class="uk-container uk-text-center">
          <h2 class="uk-heading-medium">What Our Clients Say</h2>
          <div class="uk-grid-small uk-child-width-1-2@m uk-flex-center" uk-grid>
            <div v-for="(testimonial, index) in testimonials" :key="index" class="testimonial-item">
              <div class="uk-card uk-card-default uk-card-body">
                <p>"{{ testimonial.quote }}"</p>
                <strong>- {{ testimonial.author }}</strong>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      features: [
        { title: 'Network Design & Setup', description: 'Custom network design and setup services for scalable, secure, and high-performance networks.' },
        { title: '24/7 Monitoring', description: 'Continuous monitoring and proactive maintenance to ensure network stability and uptime.' },
        { title: 'Security Management', description: 'Advanced firewall and intrusion prevention systems to protect against cyber threats.' },
        { title: 'Bandwidth Optimization', description: 'Efficient bandwidth allocation to maintain smooth and fast data flows.' },
      ],
      testimonials: [
        { quote: 'Merdeka Network provided excellent support, and our network has never been more stable.', author: 'John Doe, IT Manager' },
        { quote: 'Their proactive monitoring helped us avoid costly downtimes. Highly recommended!', author: 'Jane Smith, Operations Director' },
      ],
    };
  },
};
</script>

<style scoped>
/* Page Background */
.page-background {
  background-image: url("@/assets/backg1.jpeg"); /* Same background image as about.vue */
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

/* Section Styling */
.uk-section-muted {
  padding: 60px 20px;
  background-color: rgba(255, 255, 255, 0.9); /* Light transparent background for readability */
}

.uk-heading-medium {
  padding-top: 20px;
  font-weight: bold;
  color: #1976D2; /* Heading color matching about.vue */
}

/* Feature Card Styling */
.feature-item .uk-card {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  border-radius: 8px;
  background-color: rgba(255, 255, 255, 0.95);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-item .uk-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
}

/* Testimonial Styling */
.testimonial-item .uk-card {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  border-radius: 8px;
  background-color: rgba(255, 255, 255, 0.95);
  font-style: italic;
  color: #555;
}

.testimonial-item .uk-card strong {
  display: block;
  margin-top: 10px;
  color: #000;
}
</style>
