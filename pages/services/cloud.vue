<template>
  <div class="container">
    <!-- Service Overview -->
    <div class="section overview" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">
      <h1>Cloud Services</h1>
      <p>
        Our cloud services empower businesses with scalable, secure, and cost-effective solutions. From cloud migration
        to management, Merdeka Network provides end-to-end services tailored to fit your business needs.
      </p>
    </div>

    <!-- Cloud Solutions -->
    <div class="section solutions" uk-scrollspy="cls: uk-animation-slide-left; delay: 200; repeat: true">
      <h2>Our Cloud Solutions</h2>
      <div class="solution-list">
        <div class="solution-item" v-for="(solution, index) in cloudSolutions" :key="index">
          <h3>{{ solution.title }}</h3>
          <p>{{ solution.description }}</p>
        </div>
      </div>
    </div>

    <!-- Benefits of Cloud Services -->
    <div class="section benefits" uk-scrollspy="cls: uk-animation-slide-right; delay: 400; repeat: true">
      <h2>Why Choose Our Cloud Services?</h2>
      <ul class="benefit-list">
        <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
      </ul>
    </div>

    <!-- Customer Success Stories -->
    <div class="section testimonials" uk-scrollspy="cls: uk-animation-slide-bottom; delay: 600; repeat: true">
      <h2>Customer Success Stories</h2>
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
      cloudSolutions: [
        { title: 'Cloud Migration', description: 'Seamless migration of your infrastructure to the cloud, minimizing downtime and maximizing efficiency.' },
        { title: 'Cloud Backup & Disaster Recovery', description: 'Reliable data backup and disaster recovery solutions to protect your critical information.' },
        { title: 'Infrastructure as a Service (IaaS)', description: 'Scalable infrastructure on demand, providing cost-effective resources when you need them.' },
        { title: 'Cloud Security & Compliance', description: 'Robust security measures to ensure compliance with industry standards and protect against cyber threats.' },
      ],
      benefits: [
        'Scalability to grow with your business needs',
        'Enhanced security for data protection',
        'Cost savings through efficient resource management',
        '24/7 monitoring and support',
        'Seamless access from anywhere, anytime',
      ],
      testimonials: [
        { quote: 'Merdeka Network made our cloud migration effortless and secure. Highly recommended!', author: 'Alice Tan, CTO' },
        { quote: 'Their disaster recovery solutions saved us from a major data loss. Outstanding service!', author: 'Mark Liu, Operations Manager' },
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

.solutions, .benefits, .testimonials {
  text-align: center;
}

.solution-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.solution-item {
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
