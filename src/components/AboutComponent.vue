<template>
  <section id="about" class="about">
    <h2>{{ title }}</h2>
    <p>
      {{ text }}
    </p>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: "About me ",
      text: " Hi! I'm San — a creative frontend developer with a love for Vue, clean UI and smooth animations.",
    };
  },
};
</script>

<style scoped>
.about {
  padding: 60px 20px;
  text-align: center;
}
</style>
