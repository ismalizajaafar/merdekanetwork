<template>
  <div class="overlay">
  <div class="uk-section uk-section-muted">
    <div class="uk-container uk-text-center">
      <div class="uk-margin-large">
        <h2 class="uk-heading-medium uk-scrollspy" uk-scrollspy="cls: uk-animation-slide-top; repeat: true">Career Opportunities</h2>
        <p class="uk-text-lead uk-scrollspy" uk-scrollspy="cls: uk-animation-fade; delay: 200; repeat: true">
          Join our dynamic team and help us deliver exceptional services in PC maintenance, network solutions, and cloud computing.
        </p>
      </div>

      <div class="career-list uk-scrollspy" uk-scrollspy="cls: uk-animation-fade; delay: 300; repeat: true">
        <div 
          v-for="(position, index) in careers" 
          :key="index" 
          class="career-item uk-card uk-card-hover uk-card-body uk-margin-medium-bottom"
        >
          <h3>{{ position.title }}</h3>
          <p class="uk-text-meta"><em>{{ position.type }}</em></p>
          
          <div class="job-details">
            <p>{{ position.details }}</p>
          </div>
        </div>
      </div>

      <p class="uk-margin uk-text-lead">
        Interested candidates can apply by contacting us or sending their CV to <strong>careers@merdekanetwork.com</strong>.
      </p>
    </div>
  </div>
</div>
</template>

<script setup>
import { ref } from "vue";

const careers = ref([
  {
    title: "Network Engineer",
    type: "Full-time",
    details:
      "Design, implement, and maintain network infrastructure, including routers, switches, and firewalls. Monitor and troubleshoot network performance and ensure high availability.",
  },
  {
    title: "PC Maintenance Technician",
    type: "Full-time",
    details:
      "Perform routine checks, diagnostics, and repairs on computer hardware. Install and update software, ensure system security, and provide technical support to users.",
  },
  {
    title: "Cloud Solutions Architect",
    type: "Full-time",
    details:
      "Develop and deploy cloud architectures for scalable solutions. Collaborate with stakeholders to design secure, cost-effective systems and manage migrations to the cloud.",
  },
  {
    title: "IT Support Specialist",
    type: "Part-time",
    details:
      "Assist with day-to-day IT operations, troubleshoot technical issues, and configure software/hardware systems. Provide on-site and remote support as required.",
  },
  {
    title: "Data Analyst",
    type: "Part-time",
    details:
      "Interpret data using statistical tools, identify trends, and create dashboards/reports. Collaborate with teams to provide insights for strategic decisions.",
  },
]);
</script>
<style scoped>
.uk-section {
  background-color: rgba(255, 255, 255, 0.01);
}

.overlay {
  background-image: url("@/assets/backg3.jpeg");
  background-size: cover;
  background-attachment: fixed; /* Ensures the background remains fixed */
}

.uk-heading-medium {
  padding-top: 100px;
  font-weight: bold;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  color: #f9f9f9; /* Heading color */
}

.uk-text-lead{
  color: #f9f9f9;
  
}

.career-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.career-item {
  border: 1px solid #e5e5e5;
  border-radius: 8px;
  background-color: #fff;
  overflow: hidden;
  padding: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Static shadow */
}

.career-item h3 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 0.5rem;
}

.career-item p {
  font-size: 1rem;
  color: #666;
}

.career-item .uk-text-meta {
  font-size: 0.9rem;
  color: #999;
}

.job-details {
  font-size: 1rem;
  color: #444;
  padding-top: 10px;
}
</style>

