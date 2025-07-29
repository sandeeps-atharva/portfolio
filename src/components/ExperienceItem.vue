<template>
  <div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
      <h3 class="exp-title">{{ title }}</h3>
      <h4 class="exp-company">{{ company }}</h4>
      <ul class="exp-description">
        <li v-for="item in description" :key="item">{{ item }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ExperienceItem",
  props: {
    title: String,
    company: String,
    period: String,
    description: Array,
  },
};
</script>

<style scoped>
.timeline-item {
  position: relative;
  margin-bottom: 3rem;
  display: flex;
  align-items: center;
}

.timeline-content {
  background: white;
  padding: 2rem;
  border-radius: 20px;
  box-shadow: var(--shadow-heavy);
  width: 45%;
  position: relative;
}

.timeline-item:nth-child(odd) .timeline-content {
  margin-left: auto;
}

.timeline-dot {
  position: absolute;
  left: 50%;
  width: 20px;
  height: 20px;
  background: var(--secondary-gradient);
  border-radius: 50%;
  transform: translateX(-50%);
  z-index: 2;
}

.exp-title {
  color: #f5576c;
  font-size: 1.5rem;
}

.exp-company {
  color: #667eea;
  margin-bottom: 1rem;
}

.exp-description {
  color: #2c3e50;
  line-height: 1.8;
}

@media (max-width: 968px) {
  .timeline-content {
    width: calc(100% - 60px);
    margin-left: 60px !important;
  }

  .timeline-dot {
    left: 20px;
  }
}
</style>
