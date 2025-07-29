<!-- <template>
  <div id="app">
    <HeaderComponent />
    <HeroComponent />
    <AboutComponent />
    <SkillComponent />
    <ProjectComponent />
    <ContactComponent />
  </div>
</template>

<script>
import AboutComponent from "./components/AboutComponent.vue";
import ContactComponent from "./components/ContactComponent.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import HeroComponent from "./components/HeroComponent.vue";
import ProjectComponent from "./components/ProjectComponent.vue";
import SkillComponent from "./components/SkillComponent.vue";

export default {
  components: {
    HeaderComponent,
    HeroComponent,
    AboutComponent,
    SkillComponent,
    ProjectComponent,
    ContactComponent,
  },
};
</script>

<style>
body {
  margin: 0;
  font-family: "Segoe UI", sans-serif;
  background: #f9f9f9;
  color: #333;
}
</style> -->

<!-- App.vue -->
<template>
  <div id="app">
    <HeaderComponent />
    <HeroComponent />
    <AboutComponent />
    <SkillComponent />
    <ExperienceComponent />
    <ProjectComponent />
    <ContactComponent />
  </div>
</template>

<script>
import AboutComponent from "./components/AboutComponent.vue";
import ContactComponent from "./components/ContactComponent.vue";

import ExperienceComponent from "./components/ExperienceComponent.vue";

import HeaderComponent from "./components/HeaderComponent.vue";
import HeroComponent from "./components/HeroComponent.vue";
import ProjectComponent from "./components/ProjectComponent.vue";
import SkillComponent from "./components/SkillComponent.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    HeroComponent,
    AboutComponent,
    SkillComponent,
    ExperienceComponent,
    ProjectComponent,
    ContactComponent,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  --accent-gradient: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
  --dark-gradient: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
  --glass-bg: rgba(255, 255, 255, 0.1);
  --glass-border: rgba(255, 255, 255, 0.2);
  --text-primary: #2c3e50;
  --text-light: rgba(255, 255, 255, 0.9);
  --shadow-light: 0 8px 32px rgba(31, 38, 135, 0.37);
  --shadow-heavy: 0 20px 40px rgba(0, 0, 0, 0.1);
}

body {
  font-family: "Inter", -apple-system, BlinkMacSystemFont, sans-serif;
  line-height: 1.6;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 1;
}

.section-title {
  text-align: center;
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 3rem;
  color: var(--text-primary);
  position: relative;
}

.section-title::after {
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 4px;
  background: var(--accent-gradient);
  border-radius: 2px;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 968px) {
  .section-title {
    font-size: 2rem;
  }
}
</style>
