<template>
  <section id="experience" class="experience">
    <div class="container">
      <h2 class="section-title">Professional Journey</h2>
      <div class="timeline">
        <ExperienceItem
          v-for="(exp, index) in experiences"
          :key="index"
          :title="exp.title"
          :company="exp.company"
          :period="exp.period"
          :description="exp.description"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ExperienceItem from "./ExperienceItem.vue";

export default {
  name: "ExperienceComponent",
  components: {
    ExperienceItem,
  },
  data() {
    return {
      experiences: [
        {
          title: "Junior Frontend Developer",
          company: "Atharva System Pvt Ltd | June 2024 – Present",
          period: "2024-Present",
          description: [
            "Developed and maintained full-stack applications using the MERN stack",
            "Implemented RESTful APIs with Express.js and integrated with React frontend",
            "Enhanced application performance through React component optimization",
            "Collaborated with cross-functional teams to deliver scalable solutions",
          ],
        },
        {
          title: "MERN Stack Training",
          company: "January 2024 - June 2024",
          period: "2024",
          description: [
            "Comprehensive training in modern web development technologies",
            "Gained expertise in React Native and Next.js development",
            "Developed practical experience through hands-on projects",
            "Applied industry best practices and modern development workflows",
          ],
        },
        {
          title: "Education",
          company: "B.Tech Computer Science | Indus University | 2020-2024",
          period: "2020-2024",
          description: [
            "Graduated with strong foundation in computer science principles, algorithms, and software engineering practices.",
            "Participated in React.js workshops and development projects.",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.experience {
  padding: 100px 0;
  background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
}

.timeline {
  position: relative;
  margin-top: 3rem;
}

.timeline::before {
  content: "";
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 4px;
  background: var(--primary-gradient);
  transform: translateX(-50%);
}

@media (max-width: 968px) {
  .timeline::before {
    left: 20px;
  }
}
</style>
