<template>
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <form @submit.prevent="submitForm">
      <input v-model="name" type="text" placeholder="Your Name" required />
      <input v-model="email" type="email" placeholder="Your Email" required />
      <textarea
        v-model="message"
        placeholder="Your Message"
        required
      ></textarea>
      <button type="submit">Send</button>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  methods: {
    submitForm() {
      alert(`Thanks ${this.name}, your message has been sent!`);
      this.name = this.email = this.message = "";
    },
  },
};
</script>

<style scoped>
.contact {
  padding: 60px 20px;
  text-align: center;
}
form {
  max-width: 500px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
input,
textarea {
  padding: 12px;
  font-size: 16px;
  border-radius: 6px;
  border: 1px solid #ccc;
}
button {
  background: #42b983;
  color: white;
  padding: 12px;
  border: none;
  font-weight: bold;
  cursor: pointer;
}
</style>
