<template>
  <div class="container">
    <!-- Service Overview -->
    <div class="section overview" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">
      <h1>Our Network Services</h1>
      <p>
        At Merdeka Network, we specialize in providing robust and reliable network solutions tailored to meet the
        demands of modern businesses. Our services include network design, setup, monitoring, and support for
        enterprises of all sizes.
      </p>
    </div>

    <!-- Core Features -->
    <div class="section features" uk-scrollspy="cls: uk-animation-slide-left; delay: 200; repeat: true">
      <h2>Core Features</h2>
      <div class="feature-list">
        <div class="feature-item" v-for="(feature, index) in features" :key="index">
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.description }}</p>
        </div>
      </div>
    </div>

    <!-- Customer Testimonials -->
    <div class="section testimonials" uk-scrollspy="cls: uk-animation-slide-right; delay: 400; repeat: true">
      <h2>What Our Clients Say</h2>
      <div class="testimonial-list">
        <div class="testimonial-item" v-for="(testimonial, index) in testimonials" :key="index">
          <p>"{{ testimonial.quote }}"</p>
          <strong>- {{ testimonial.author }}</strong>
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
.container {
  padding: 20px;
}

.section {
  margin-bottom: 40px;
  padding-top: 100px;
}

.overview {
  text-align: center;
  max-width: 800px;
  margin: auto;
}

.features {
  text-align: center;
}

.feature-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.feature-item {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 250px;
  text-align: center;
}

.testimonials {
  text-align: center;
}

.testimonial-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
  align-items: center;
}

.testimonial-item {
  max-width: 600px;
  font-style: italic;
  color: #555;
}
</style>
