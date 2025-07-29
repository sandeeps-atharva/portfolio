<template>
  <div class="project-card">
    <div class="project-header">
      <h3 class="project-title">{{ title }}</h3>
      <p class="project-tech">{{ tech }}</p>
    </div>
    <div class="project-content">
      <p class="project-description">{{ description }}</p>
      <ul class="project-features">
        <li v-for="feature in features" :key="feature">{{ feature }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    title: String,
    tech: String,
    description: String,
    features: Array,
  },
};
</script>

<style scoped>
.project-card {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: var(--shadow-heavy);
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-10px);
}

.project-header {
  background: var(--secondary-gradient);
  color: white;
  padding: 2rem;
}

.project-title {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.project-tech {
  font-size: 0.9rem;
  opacity: 0.9;
}

.project-content {
  padding: 2rem;
}

.project-description {
  color: var(--text-primary);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.project-features {
  list-style: none;
  margin-bottom: 2rem;
}

.project-features li {
  color: var(--text-primary);
  padding: 0.25rem 0;
  position: relative;
  padding-left: 1.5rem;
}

.project-features li::before {
  content: "✓";
  position: absolute;
  left: 0;
  color: #27ca3f;
  font-weight: bold;
}
</style>
