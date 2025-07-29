<template>
  <section id="about" class="about">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      <div class="about-grid">
        <div class="about-content">
          <p class="about-text">{{ aboutText1 }}</p>

          <div class="stats-grid">
            <div v-for="stat in stats" :key="stat.label" class="stat-item">
              <span class="stat-number">{{ stat.number }}</span>
              <span class="stat-label">{{ stat.label }}</span>
            </div>
          </div>

          <p class="about-text">{{ aboutText2 }}</p>
        </div>

        <CodeSnippet />
      </div>
    </div>
  </section>
</template>

<script>
import CodeSnippet from "./CodeSnippet.vue";

export default {
  name: "AboutComponent",
  components: {
    CodeSnippet,
  },
  data() {
    return {
      aboutText1:
        "I'm a passionate Frontend Developer with 2 years of combined training and professional experience. Currently working at Atharva System Pvt Ltd, I specialize in building scalable, responsive web applications using the MERN stack. My expertise spans from React.js and Next.js to Shopify custom app development.",
      aboutText2:
        "I'm passionate about performance optimization, cross-functional collaboration, and delivering innovative web solutions. Always eager to learn new technologies and tackle challenging problems.",
      stats: [
        { number: "2+", label: "Years Experience" },
        { number: "20+", label: "Projects Built" },
        { number: "10+", label: "Technologies" },
      ],
    };
  },
};
</script>

<style scoped>
.about {
  padding: 100px 0;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  position: relative;
}

.about::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(
      circle at 70% 20%,
      rgba(102, 126, 234, 0.1) 0%,
      transparent 50%
    ),
    radial-gradient(
      circle at 30% 80%,
      rgba(118, 75, 162, 0.1) 0%,
      transparent 50%
    );
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.about-content {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  padding: 3rem;
  box-shadow: var(--shadow-light);
}

.about-text {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  color: var(--text-primary);
  line-height: 1.8;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin: 2rem 0;
}

.stat-item {
  text-align: center;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 15px;
  backdrop-filter: blur(10px);
}

.stat-number {
  font-size: 2rem;
  font-weight: 700;
  color: #f5576c;
  display: block;
}

.stat-label {
  font-size: 0.9rem;
  color: var(--text-primary);
  font-weight: 500;
}

@media (max-width: 968px) {
  .about-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .stats-grid {
    grid-template-columns: 1fr;
  }
}
</style>
