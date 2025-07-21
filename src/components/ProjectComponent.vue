<template>
  <section id="project" class="projects">
    <h2>Projects</h2>
    <div class="project-list">
      <div
        class="project-card"
        v-for="(project, index) in projects"
        :key="index"
      >
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <a :href="project.link" target="_blank">View Project</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Todo App",
          description: "A Vue + Firebase todo list app.",
          link: "#",
        },
        {
          title: "Portfolio Site",
          description: "Personal website built with Vue.",
          link: "#",
        },
        {
          title: "Weather App",
          description: "Weather data via OpenWeatherMap API.",
          link: "#",
        },
      ],
    };
  },
};
</script>

<style scoped>
.projects {
  padding: 60px 20px;
  text-align: center;
}
.project-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}
.project-card {
  width: 280px;
  background: white;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 12px;
}
a {
  color: #42b983;
  text-decoration: none;
  font-weight: bold;
}
</style>
