<template>
  <div class="background">
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview">
        <h1 class="fade-in uk-heading-medium">PC Maintenance Services</h1>
        <p class="fade-in desc">
          Merdeka Network offers comprehensive PC maintenance services to ensure your systems run efficiently and securely. Our expert team provides regular upkeep, troubleshooting, and repair services tailored to meet your business or personal needs.
        </p>
      </div>

      <!-- Types of PC Maintenance Services -->
      <div class="section services">
        <h2 class="fade-in pcmservice">Our PC Maintenance Services</h2>
        <div class="service-list">
          <div class="service-item fade-in" v-for="(service, index) in pcServices" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>

      <!-- Service Benefits -->
      <div class="section benefits">
        <h2 class="fade-in">Benefits of Our PC Maintenance Services</h2>
        <ul class="benefit-list fade-in">
          <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
        </ul>
      </div>

      <!-- Client Testimonials -->
      <div class="section testimonials">
        <h2 class="fade-in pcmservice">What Our Clients Say</h2>
        <div class="testimonial-list">
          <div class="testimonial-item fade-in" v-for="(testimonial, index) in testimonials" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
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
      pcServices: [
        { title: 'Regular Cleaning & Dust Removal', description: 'Prevent hardware issues by keeping components clean and dust-free.' },
        { title: 'Hardware Diagnostics & Repair', description: 'Identify and resolve hardware issues to keep your PC running smoothly.' },
        { title: 'Software Updates & Optimization', description: 'Optimize system performance with the latest updates and software configurations.' },
        { title: 'Virus & Malware Removal', description: 'Ensure system security by removing malicious software and preventing future infections.' },
        { title: 'Data Backup & Recovery', description: 'Protect critical data with backup solutions and data recovery services.' },
      ],
      benefits: [
        'Extended lifespan of PC hardware',
        'Improved system performance and speed',
        'Enhanced data security and protection',
        'Reduced downtime and productivity loss',
        'Proactive identification and resolution of issues',
      ],
      testimonials: [
        { quote: 'Merdeka Network’s maintenance services have kept our office PCs running efficiently and securely.', author: '' },
        { quote: 'Their virus removal and performance optimization significantly improved our workflow.', author: '' },
      ],
    };
  },
};
</script>

<style scoped>
.background {
  background-image: url("@/assets/backg3.jpeg");
  background-size: cover;
  background-position: center;
}

.desc{
  color: #f9f9f9;
}

.pcmservice{
  color: #f9f9f9;
}

.container {
  padding: 20px;
  /* background-color: rgba(255, 255, 255, 0.2); */
  animation: fadeIn 1s ease-out;
}
.uk-heading-medium{
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #f9f9f9; /* Heading color */
}

.section {
  margin-bottom: 40px;
  padding-top: 40px;
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}
.benefits{
  background-color: rgba(255, 255, 255, 0.92);
  padding-bottom: 20px;
  border-radius: 10px;
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

.overview {
  padding-top: 100px;
  text-align: center;
}

.services, .benefits, .testimonials {
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

.benefit-list {
  list-style-type: none;
  padding: 0;
  max-width: 600px;
  margin: auto;
  text-align: left;
  display: inline-block;
}

.benefit-list li {
  padding: 10px 0;
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
