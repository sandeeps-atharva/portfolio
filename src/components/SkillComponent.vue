<template>
  <section id="skills" class="skills">
    <div class="container">
      <h2 class="section-title white-title">Technical Skills</h2>
      <div class="skills-grid">
        <SkillCard
          v-for="skill in skills"
          :key="skill.title"
          :icon="skill.icon"
          :title="skill.title"
          :items="skill.items"
        />
      </div>
    </div>
  </section>
</template>

<script>
import SkillCard from "./SkillCard.vue";

export default {
  name: "SkillComponent",
  components: {
    SkillCard,
  },
  data() {
    return {
      skills: [
        {
          icon: "⚛️",
          title: "Frontend",
          items: [
            "React.js",
            "Next.js",
            "JavaScript ES6+",
            "HTML5",
            "CSS3",
            "React Native",
          ],
        },
        {
          icon: "⚙️",
          title: "Backend & Database",
          items: [
            "Node.js",
            "Express.js",
            "MongoDB",
            "RESTful APIs",
            "GraphQL",
          ],
        },
        {
          icon: "🛒",
          title: "E-commerce & CMS",
          items: ["Shopify Apps", "Shopify API", "TakeShape CMS"],
        },
        {
          icon: "🔧",
          title: "Tools & Practices",
          items: [
            "Git",
            "Agile",
            "Performance Optimization",
            "Responsive Design",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills {
  padding: 100px 0;
  background: var(--dark-gradient);
  color: white;
}

.white-title {
  color: white;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
