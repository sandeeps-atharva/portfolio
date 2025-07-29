<template>
  <section id="projects" class="projects">
    <div class="container">
      <h2 class="section-title">Featured Projects</h2>
      <div class="projects-grid">
        <ProjectCard
          v-for="project in projects"
          :key="project.title"
          :title="project.title"
          :tech="project.tech"
          :description="project.description"
          :features="project.features"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ProjectCard from "./ProjectCard.vue";

export default {
  name: "ProjectComponent",
  components: {
    ProjectCard,
  },
  data() {
    return {
      projects: [
        {
          title: "Zulu8 Shopify App",
          tech: "Shopify API • React.js • Node.js • Express.js",
          description:
            "A comprehensive discount application that boosts sales through strategic upsell messaging and advanced pricing strategies.",
          features: [
            "Quantity-based discounts (Buy 2 Get 5% Off)",
            "Amount-based discounts (Spend $50 Get 5% Off)",
            "BOGO functionality with multiple options",
            "Customizable widgets for quantity breaks",
            "Multi-language support for global accessibility",
            "Seamless integration with existing discount codes",
          ],
        },
        {
          title: "Earth's Splendor E-commerce",
          tech: "Next.js • TakeShape CMS • Shopify • REST APIs",
          description:
            "A responsive e-commerce website built with Next.js, featuring optimal performance and SEO optimization.",
          features: [
            "Server-side rendering with Next.js",
            "Content management with TakeShape CMS",
            "Shopify integration for e-commerce functionality",
            "Responsive design for all devices",
            "SEO optimized pages",
            "Fast loading performance",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.projects {
  padding: 100px 0;
  background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>
