<template>
  <div class="background">
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview">
        <h1 class="fade-in uk-heading-medium">Data Analysis Services</h1>
        <p class="fade-in title">
          Merdeka Network provides top-notch data analysis services, transforming raw data into actionable insights. From predictive analytics to visualization, we deliver solutions that drive smarter business decisions.
        </p>
      </div>

      <!-- Types of Data Analysis Services -->
      <div class="section services">
        <h2 class="fade-in data-service">Our Data Analysis Services</h2>
        <div class="service-list">
          <div class="service-item fade-in" v-for="(service, index) in dataServices" :key="index" :style="{ animationDelay: `${index * 0.2}s` }">
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>

      <!-- Service Benefits -->
      <div class="section benefits">
        <h2 class="fade-in">Benefits of Our Data Analysis Services</h2>
        <ul class="benefit-list fade-in">
          <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
        </ul>
      </div>

      <!-- Client Testimonials -->
      <div class="section testimonials">
        <h2 class="fade-in title">What Our Clients Say</h2>
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
      dataServices: [
        { title: 'Data Collection & Cleaning', description: 'Gather and clean data to ensure accuracy and usability for analysis.' },
        { title: 'Predictive Analytics', description: 'Develop models to forecast trends and inform decision-making.' },
        { title: 'Data Visualization', description: 'Create intuitive charts and dashboards to make complex data accessible.' },
        { title: 'Business Intelligence Reporting', description: 'Deliver actionable insights through clear and concise reporting.' },
        { title: 'Customized Analytical Solutions', description: 'Tailor analytics solutions to meet specific business needs.' },
      ],
      benefits: [
        'Turn raw data into actionable insights',
        'Make informed business decisions',
        'Optimize processes and operations',
        'Identify trends and patterns in your data',
        'Improve efficiency and reduce costs',
      ],
      testimonials: [
        { quote: 'Merdeka Network’s data analysis transformed how we make decisions.', author: 'John D., Business Analyst' },
        { quote: 'Their predictive analytics helped us stay ahead of market trends.', author: 'Linda S., Marketing Manager' },
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

.container {
  padding: 20px;
  /* background-color: rgba(255, 255, 255, ); */
  animation: fadeIn 1s ease-out;
}
.uk-heading-medium {
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #f9f9f9; /* Heading color */
}
.title{
  color: #f9f9f9;
}

.data-service{
  color: #f9f9f9;
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

.overview {
  padding-top: 100px;
  text-align: center;
}

.services, .benefits, .testimonials {
  text-align: center;
  color: #555;
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
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.7);
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