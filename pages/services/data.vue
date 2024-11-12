<template>
  <div class="container">
    <!-- Service Overview -->
    <div class="section overview">
      <h1 class="fade-in">Data Analysis Services</h1>
      <p class="fade-in">
        At Merdeka Network, we provide comprehensive data analysis services that empower businesses to make informed decisions.
        From data collection and cleaning to predictive analytics and reporting, we transform raw data into valuable insights.
      </p>
    </div>

    <!-- Core Services -->
    <div class="section services">
      <h2 class="fade-in">Our Data Analysis Services</h2>
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

    <!-- Key Benefits -->
    <div class="section benefits">
      <h2 class="fade-in">Why Choose Our Data Analysis Services?</h2>
      <ul class="benefit-list fade-in">
        <li v-for="(benefit, index) in benefits" :key="index">{{ benefit }}</li>
      </ul>
    </div>

    <!-- Case Studies / Success Stories -->
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

    <!-- Call to Action -->
    <div class="section cta">
      <h2 class="fade-in">Get Started with Data Insights Today</h2>
      <p class="fade-in">Contact us to discuss how we can turn your data into actionable insights and strategies.</p>
      <button class="fade-in" @click="navigateToContact">Contact Us</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      services: [
        {
          title: "Data Collection & Cleaning",
          description:
            "We gather data from multiple sources and clean it to ensure accuracy, consistency, and completeness.",
        },
        {
          title: "Predictive Analytics",
          description:
            "Our predictive models help forecast future trends, giving you a competitive edge in decision-making.",
        },
        {
          title: "Business Intelligence (BI) Reporting",
          description:
            "We deliver actionable reports and dashboards that provide clear insights into your business performance.",
        },
        {
          title: "Data Visualization",
          description:
            "Transform complex datasets into intuitive, visual representations to simplify decision-making.",
        },
      ],
      benefits: [
        "Unlock valuable insights from complex data",
        "Make data-driven decisions that improve business outcomes",
        "Increase operational efficiency and reduce costs",
        "Enhance customer experience through data personalization",
        "Leverage predictive analytics for smarter business strategies",
      ],
      caseStudies: [
        {
          title: "Improved Customer Retention with Predictive Analytics",
          description:
            "By analyzing customer behavior, we helped a retail client predict churn and improve retention through targeted campaigns.",
          client: "Retail Corp.",
        },
        {
          title: "Optimizing Inventory Management for Supply Chain Efficiency",
          description:
            "We analyzed supply chain data to optimize inventory levels, reducing costs and improving delivery times for a logistics company.",
          client: "Logistics Solutions Inc.",
        },
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
/* Global Styling */
.container {
  padding: 20px;
  animation: fadeIn 1s ease-out;
}

.section {
  padding-top: 100px;
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

.overview {
  text-align: center;
}

.services {
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
  transform: translateY(30px);
  opacity: 0;
  animation: fadeInUp 0.8s ease-out forwards;
}

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

.cta {
  text-align: center;
}

.cta button {
  background-color: #42a5f5;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transform: translateY(30px);
  opacity: 0;
  animation: fadeInUp 0.8s ease-out forwards;
}

.cta button:hover {
  background-color: #2196f3;
}

/* Keyframe Animations */
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

/* Add slight delays to the fade-in effect for each item */
.fade-in {
  animation: fadeIn 1s ease-out forwards;
}

.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}
</style>
