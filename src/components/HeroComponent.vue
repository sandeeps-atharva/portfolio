<template>
  <section id="home" class="hero">
    <h1>
      Hey, I'm <span>{{ name }}</span>
    </h1>
    <p>{{ HeroText }}</p>
    <button @click="scrollToContact">Contact Me</button>
  </section>
</template>

<script>
export default {
  data() {
    return { name: "San", HeroText: "A Passionate Vue.js Developer" };
  },
  methods: {
    scrollToContact() {
      document.getElementById("contact").scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.hero {
  padding: 100px 20px;
  text-align: center;
  background: linear-gradient(135deg, #42b983, #35495e);
  color: white;
}
h1 span {
  color: #ffe100;
}
button {
  margin-top: 20px;
  padding: 10px 20px;
  background: white;
  color: #42b983;
  border: none;
  font-weight: bold;
  cursor: pointer;
}
</style>
