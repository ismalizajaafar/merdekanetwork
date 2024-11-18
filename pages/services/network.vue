<template>
  <div class="background">
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview">
        <h1 class="fade-in uk-heading-medium">Our Network Services</h1>
        <p class="fade-in desc">
          At Merdeka Network, we specialize in providing robust and reliable network solutions tailored to meet the
          demands of modern businesses. Our services include network design, setup, monitoring, and support for
          enterprises of all sizes.
        </p>
      </div>

      <!-- Core Features -->
      <div class="section services">
        <h2 class="fade-in corefeat">Core Features</h2>
        <div class="service-list">
          <div 
            class="service-item fade-in" 
            v-for="(feature, index) in features" 
            :key="index" 
            :style="{ animationDelay: `${index * 0.2}s` }"
          >
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.description }}</p>
          </div>
        </div>
      </div>

      <!-- Client Testimonials -->
      <div class="section testimonials">
        <h2 class="fade-in feedb">What Our Clients Say</h2>
        <div class="testimonial-list">
          <div 
            class="testimonial-item fade-in" 
            v-for="(testimonial, index) in testimonials" 
            :key="index" 
            :style="{ animationDelay: `${index * 0.2}s` }"
          >
            <p>"{{ testimonial.quote }}"</p>
            <strong>- {{ testimonial.author }}</strong>
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
/* Background */
.background {
  background-image: url("@/assets/backg3.jpeg");
  background-size: cover;
  background-position: center;
}

/* Container and Sections */
.container {
  padding: 20px;
  /* background-color: rgba(255, 255, 255, 0.2); */
  border-radius: 10px;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.3);
}

.desc{
  color: #f9f9f9;
}

.corefeat{
  color: #f9f9f9;
}

.feedb{
  color: #f9f9f9;
}

.uk-heading-medium {
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #f9f9f9; /* Heading color */
}

.section {
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

.overview {
  text-align: center;
  padding-top: 80px;
}

.services, .testimonials {
  text-align: center;
  color: #333;
}

.service-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.service-item {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.7);
  width: 250px;
  text-align: center;
  transform: translateY(30px);
  opacity: 0;
  animation: fadeInUp 0.8s ease-out forwards;
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
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.7);
}

/* Animations */
@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes fadeInUp {
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn 1s ease-out forwards;
}

.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}
</style>
