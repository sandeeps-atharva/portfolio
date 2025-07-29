<template>
  <div class="skill-card">
    <div class="skill-header">
      <span class="skill-icon">{{ icon }}</span>
      <h3 class="skill-title">{{ title }}</h3>
    </div>
    <div class="skill-items">
      <span v-for="item in items" :key="item" class="skill-tag">{{
        item
      }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "SkillCard",
  props: {
    icon: String,
    title: String,
    items: Array,
  },
};
</script>

<style scoped>
.skill-card {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  padding: 2rem;
  transition: transform 0.3s ease;
}

.skill-card:hover {
  transform: translateY(-10px);
}

.skill-header {
  display: flex;
  align-items: center;
  margin-bottom: 1.5rem;
  gap: 1rem;
}

.skill-icon {
  font-size: 2rem;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.3));
}

.skill-title {
  font-size: 1.4rem;
  font-weight: 600;
}

.skill-items {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.skill-tag {
  background: var(--accent-gradient);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: transform 0.2s ease;
}

.skill-tag:hover {
  transform: scale(1.05);
}
</style>
