<template>
  <section id="hero" class="hero">
    <div class="hero-content">
      <h1 class="hero-title">
        Hey, I'm <span class="highlight">{{ name }}</span>
      </h1>
      <h2 class="hero-subtitle">{{ role }}</h2>
      <p class="hero-description">{{ description }}</p>
      <a href="#contact" class="cta-button">Let's Connect</a>
    </div>
  </section>
</template>

<script>
export default {
  name: "HeroComponent",
  data() {
    return {
      name: "Sandeep Suthar",
      role: "Junior Frontend Developer",
      description:
        "Transforming ideas into interactive digital experiences with React, Next.js, and modern web technologies. Based in Ahmedabad, crafting the future of web development one component at a time. ☕💻",
    };
  },
};
</script>

<style scoped>
.hero {
  height: 100vh;
  background: var(--primary-gradient);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(
      circle at 20% 80%,
      rgba(120, 119, 198, 0.3) 0%,
      transparent 50%
    ),
    radial-gradient(
      circle at 80% 20%,
      rgba(255, 255, 255, 0.1) 0%,
      transparent 50%
    );
}

.hero-content {
  position: relative;
  z-index: 1;
  max-width: 800px;
  padding: 0 2rem;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  margin-bottom: 1rem;
  opacity: 0;
  animation: fadeInUp 1s ease 0.3s forwards;
}

.highlight {
  color: #feca57;
}

.hero-subtitle {
  font-size: clamp(1.2rem, 2.5vw, 1.5rem);
  margin-bottom: 2rem;
  opacity: 0;
  animation: fadeInUp 1s ease 0.6s forwards;
}

.hero-description {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0;
  animation: fadeInUp 1s ease 0.9s forwards;
  color: var(--text-light);
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  text-decoration: none;
  border-radius: 50px;
  font-weight: 600;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  transition: all 0.3s ease;
  opacity: 0;
  animation: fadeInUp 1s ease 1.2s forwards;
}

.cta-button:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
  box-shadow: var(--shadow-light);
}
</style>
