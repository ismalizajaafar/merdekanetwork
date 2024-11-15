<template>
  <div class="background">
    <div class="container">
      <!-- Service Overview -->
      <div class="section overview">
        <h1 class="fade-in uk-heading-medium">Data Analysis Services</h1>
        <p class="fade-in">
          At Merdeka Network, we provide comprehensive data analysis services that empower businesses to make informed decisions.
          From data collection and cleaning to predictive analytics and reporting, we transform raw data into valuable insights.
        </p>
      </div>

      <!-- Core Services -->
      <div class="section services">
        <h2 class="fade-in uk-heading-small">Our Data Analysis Services</h2>
        <div class="service-list">
          <div 
            class="service-item fade-in" 
            v-for="(service, index) in services" 
            :key="index"
            :style="{ animationDelay: `${index * 0.2}s` }"
          >
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>
      
      <div class="middle-section">
        <!-- Key Benefits -->
        <div class="section benefits">
          <h2 class="fade-in">Why Choose Our Data Analysis Services?</h2>
          <ul class="benefit-list fade-in">
            <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
          </ul>
        </div>
      
        <!-- Case Studies / Success Stories -->
        <!-- <div class="low-section>" -->
         <div class="section case-studies">
          <h2 class="fade-in">Case Studies & Success Stories</h2>
          <div class="case-study-list">
            <div 
              class="case-study-item fade-in" 
              v-for="(caseStudy, index) in caseStudies" 
              :key="index"
              :style="{ animationDelay: `${index * 0.2}s` }"
            >
              <h3>{{ caseStudy.title }}</h3>
              <p>{{ caseStudy.description }}</p>
              <strong>- {{ caseStudy.client }}</strong>
            </div>
          </div>
        </div>
      </div>
      </div>
      

      <!-- Call to Action -->
      <div class="section cta">
        <h2 class="fade-in">Get Started with Data Insights Today</h2>
        <p class="fade-in">Contact us to discuss how we can turn your data into actionable insights and strategies.</p>
        <button class="cta-button fade-in" @click="navigateToContact">Contact Us</button>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      services: [
        { title: "Data Collection & Cleaning", description: "We gather data from multiple sources and clean it to ensure accuracy, consistency, and completeness." },
        { title: "Predictive Analytics", description: "Our predictive models help forecast future trends, giving you a competitive edge in decision-making." },
        { title: "Business Intelligence (BI) Reporting", description: "We deliver actionable reports and dashboards that provide clear insights into your business performance." },
        { title: "Data Visualization", description: "Transform complex datasets into intuitive, visual representations to simplify decision-making." },
      ],
      benefits: [
        "Unlock valuable insights from complex data",
        "Make data-driven decisions that improve business outcomes",
        "Increase operational efficiency and reduce costs",
        "Enhance customer experience through data personalization",
        "Leverage predictive analytics for smarter business strategies",
      ],
      caseStudies: [
        { title: "Improved Customer Retention with Predictive Analytics", description: "By analyzing customer behavior, we helped a retail client predict churn and improve retention through targeted campaigns.", client: "Retail Corp." },
        { title: "Optimizing Inventory Management for Supply Chain Efficiency", description: "We analyzed supply chain data to optimize inventory levels, reducing costs and improving delivery times for a logistics company.", client: "Logistics Solutions Inc." },
      ],
    };
  },
  methods: {
    navigateToContact() {
      this.$router.push({ name: "contact" });
    },
  },
};
</script>

<style scoped>
/* Background */
.background {
  background-image: url("@/assets/backg1.jpeg");
  background-size: cover;
  background-position: center;
}

/* Container and Sections */
.container {
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 10px;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.3);
}
.uk-heading-medium{
  padding-top: 30px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #1976D2; /* Heading color */
}

.uk-heading-small{
  font-weight: 400;
}
.section {
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

/* Service Overview */
.overview {
  text-align: center;
  padding-top: 80px;
}

/* Service List */
.service-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.service-item {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
  width: 250px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  animation: fadeInUp 0.8s ease-out forwards;
}

.service-item:hover {
  transform: translateY(-5px);
  box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.2);
}

/* Benefits */
.benefits {
  text-align: center;
}

.benefit-list {
  list-style-type: none;
  padding: 0;
  max-width: 600px;
  margin: auto;
}

.benefit-list li {
  padding: 10px 0;
}

/* Lower Section */
.lower-section {
  background-color: #ffffff;
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  padding: 20px;
}

/* Case Studies */
.case-studies {
  text-align: center;
}

.case-study-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
  align-items: center;
}

.case-study-item {
  max-width: 600px;
  font-style: italic;
  color: #555;
}

/* CTA */
.cta {
  text-align: center;
}

.cta-button {
  background-color: #1976d2;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.cta-button:hover {
  background-color: #1565c0;
  transform: translateY(-2px);
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

/* Fade-in class for delayed animations */
.fade-in {
  animation: fadeIn 1s ease-out forwards;
}

.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}
</style>
