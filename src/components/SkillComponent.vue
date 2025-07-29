<template>
  <section id="skill" class="skills">
    <h2>My Skills</h2>
    <div class="skills-grid">
      <div v-for="(section, index) in skills" :key="index" class="skill-block">
        <div class="skill-header">
          <span class="skill-icon">{{ section.icon }}</span>
          <h3 class="skill-title">{{ section.title }}</h3>
        </div>
        <div class="skills-list">
          <span v-for="(item, i) in section.items" :key="i" class="skill-item">
            {{ item }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          title: "Frontend",
          icon: "🖥️",
          items: [
            "Vue.js",
            "HTML5",
            "CSS3",
            "Tailwind",
            "Bootstrap",
            "React.js",
            "Next.js",
            "Shopify App Development",
          ],
        },
        {
          title: "Backend",
          icon: "⚙️",
          items: ["PHP", "Node.js", "Laravel", "Odoo"],
        },
        {
          title: "Database",
          icon: "🗄️",
          items: ["MySQL", "MongoDB"],
        },
        {
          title: "Tools",
          icon: "🔧",
          items: ["Git", "Figma", "VS Code", "Postman"],
        },
        {
          title: "Soft Skills",
          icon: "📚",
          items: ["Problem-solving", "Time Management", "Documentation Jedi"],
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills {
  padding: 60px 20px;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  min-height: 100vh;
}

.skills h2 {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  color: #2c3e50;
  font-weight: 700;
  position: relative;
}

.skills h2::after {
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
  border-radius: 2px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.skill-block {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 16px;
  padding: 2rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}

.skill-block:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.skill-header {
  display: flex;
  align-items: center;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 2px solid #f1f3f4;
}

.skill-icon {
  font-size: 2rem;
  margin-right: 1rem;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.1));
}

.skill-title {
  font-size: 1.4rem;
  font-weight: 600;
  color: #2c3e50;
  margin: 0;
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.skill-item {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  cursor: default;
  box-shadow: 0 2px 8px rgba(102, 126, 234, 0.3);
}

.skill-item:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
}

/* Responsive Design */
@media (max-width: 768px) {
  .skills {
    padding: 40px 15px;
  }

  .skills h2 {
    font-size: 2rem;
    margin-bottom: 2rem;
  }

  .skills-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .skill-block {
    padding: 1.5rem;
  }

  .skill-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }

  .skill-icon {
    margin-right: 0;
    margin-bottom: 0.5rem;
  }
}

@media (max-width: 480px) {
  .skills {
    padding: 30px 10px;
  }

  .skill-block {
    padding: 1.2rem;
  }

  .skills-list {
    gap: 0.5rem;
  }

  .skill-item {
    padding: 0.4rem 0.8rem;
    font-size: 0.8rem;
  }
}
</style>
