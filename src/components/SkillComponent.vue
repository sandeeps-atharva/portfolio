<template>
  <section id="skill" class="skills">
    <h2>My Skills</h2>
    <div>
      <div v-for="(section, index) in skills" :key="index" class="skill-block">
        <h3>{{ section.icon }} {{ section.title }}</h3>
        <ul>
          <li v-for="(item, i) in section.items" :key="i">{{ item }}</li>
        </ul>
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
            "React js",
            "Next js ",
            "Shopify App development",
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
          icon: "🎨",
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
  background: #eee;
  text-align: center;
}
ul {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  list-style: none;
  padding: 0;
}
li {
  background: white;
  padding: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
}
</style>
