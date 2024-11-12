<template>
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview">
        <h1>PC Maintenance Services</h1>
        <p>Merdeka Network offers comprehensive PC maintenance services to ensure your systems run efficiently and securely. Our expert team provides regular upkeep, troubleshooting, and repair services tailored to meet your business or personal needs.</p>
      </div>
  
      <!-- Types of PC Maintenance Services -->
      <div class="section services">
        <h2>Our PC Maintenance Services</h2>
        <div class="service-list">
          <div class="service-item" v-for="(service, index) in pcServices" :key="index">
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>
  
      <!-- Service Benefits -->
      <div class="section benefits">
        <h2>Benefits of Our PC Maintenance Services</h2>
        <ul class="benefit-list">
          <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
        </ul>
      </div>
  
      <!-- Client Testimonials -->
      <div class="section testimonials">
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
          { quote: 'Merdeka Network’s maintenance services have kept our office PCs running efficiently and securely.', author: 'Carlos M., Office Manager' },
          { quote: 'Their virus removal and performance optimization significantly improved our workflow.', author: 'Sarah L., Freelance Designer' },
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
  
  .services, .benefits, .testimonials {
    text-align: center;
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
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 250px;
    text-align: center;
  }
  
  .benefit-list {
    list-style-type: none;
    padding: 0;
    text-align: left;
    max-width: 600px;
    margin: auto;
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
  </style>
  