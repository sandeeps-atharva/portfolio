<template>
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
</style>
