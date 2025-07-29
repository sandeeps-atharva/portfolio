<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title white-title">Get In Touch</h2>
      <div class="contact-grid">
        <div class="contact-info">
          <h3 class="contact-title">Let's Connect!</h3>
          <div
            class="contact-item"
            v-for="item in contactItems"
            :key="item.label"
          >
            <span class="contact-icon">{{ item.icon }}</span>
            <span>{{ item.value }}</span>
          </div>
        </div>

        <ContactForm />
      </div>
    </div>
  </section>
</template>

<script>
import ContactForm from "./ContactForm.vue";

export default {
  name: "ContactComponent",
  components: {
    ContactForm,
  },
  data() {
    return {
      contactItems: [
        { icon: "📧", label: "Email", value: "sandeep@example.com" },
        { icon: "📱", label: "Phone", value: "+91 98765 43210" },
        { icon: "📍", label: "Location", value: "Ahmedabad, Gujarat" },
        {
          icon: "💼",
          label: "LinkedIn",
          value: "linkedin.com/in/sandeep-suthar",
        },
      ],
    };
  },
};
</script>

<style scoped>
.contact {
  padding: 100px 0;
  background: var(--primary-gradient);
  color: white;
  text-align: center;
}

.white-title {
  color: white;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-top: 3rem;
  align-items: start;
}

.contact-info {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  padding: 3rem;
}

.contact-title {
  font-size: 2rem;
  margin-bottom: 2rem;
  color: white;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.contact-icon {
  font-size: 1.5rem;
}

@media (max-width: 968px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
</style>
