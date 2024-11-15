<template>
  <div class="background">
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview fade-in">
        <h1 class="uk-heading-medium">Cloud Services</h1>
        <p>
          Our cloud services empower businesses with scalable, secure, and cost-effective solutions. From cloud migration to management, Merdeka Network provides end-to-end services tailored to fit your business needs.
        </p>
      </div>

      <!-- Cloud Solutions -->
      <div class="section solutions fade-in-up">
        <h2>Our Cloud Solutions</h2>
        <div class="solution-list">
          <div class="solution-item" v-for="(solution, index) in cloudSolutions" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
            <h3>{{ solution.title }}</h3>
            <p>{{ solution.description }}</p>
          </div>
        </div>
      </div>

      <!-- Benefits of Cloud Services -->
      <div class="section benefits fade-in-up">
        <h2>Why Choose Our Cloud Services?</h2>
        <ul class="benefit-list">
          <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
        </ul>
      </div>

      <!-- Customer Success Stories -->
      <div class="section testimonials fade-in">
        <h2>Customer Success Stories</h2>
        <div class="testimonial-list">
          <div class="testimonial-item" v-for="(testimonial, index) in testimonials" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
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
.background {
  background-image: url("@/assets/backg1.jpeg");
  background-size: cover;
  background-position: center;
}

.container {
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.2);
  animation: fadeIn 1s ease-out;
}

.uk-heading-medium{
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #1976D2; /* Heading color */
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

.testimonials{
  background-color: rgba(255, 255, 255, 0.92);
  padding-bottom: 20px;
  border-radius: 10px;
}

.overview {
  padding-top: 100px;
  text-align: center;
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
