<template>
  <form class="contact-form" @submit.prevent="submitForm">
    <h3 class="form-title">Send Message</h3>

    <div class="form-group">
      <input
        v-model="form.name"
        type="text"
        class="form-input"
        placeholder="Your Name"
        required
      />
    </div>

    <div class="form-group">
      <input
        v-model="form.email"
        type="email"
        class="form-input"
        placeholder="Your Email"
        required
      />
    </div>

    <div class="form-group">
      <input
        v-model="form.subject"
        type="text"
        class="form-input"
        placeholder="Subject"
        required
      />
    </div>

    <div class="form-group">
      <textarea
        v-model="form.message"
        class="form-input form-textarea"
        placeholder="Your Message"
        required
      ></textarea>
    </div>

    <button type="submit" class="submit-btn" :disabled="isSubmitting">
      {{ isSubmitting ? "Sending..." : "Send Message" }}
    </button>

    <div v-if="submitMessage" class="submit-message" :class="submitStatus">
      {{ submitMessage }}
    </div>
  </form>
</template>

<script>
export default {
  name: "ContactForm",
  data() {
    return {
      form: {
        name: "",
        email: "",
        subject: "",
        message: "",
      },
      isSubmitting: false,
      submitMessage: "",
      submitStatus: "",
    };
  },
  methods: {
    async submitForm() {
      this.isSubmitting = true;
      this.submitMessage = "";

      const { name, email, subject, message } = this.form;

      // Format WhatsApp message
      const whatsappText = `
    *New Contact Message*%0A
    👤 *Name:* ${name}%0A
    📧 *Email:* ${email}%0A
    📝 *Subject:* ${subject}%0A
    💬 *Message:* ${message}
  `.trim();

      const phone = "917665769959"; // your WhatsApp number (NO + or leading 0)
      const url = `https://wa.me/${phone}?text=${encodeURIComponent(
        whatsappText
      )}`;

      // Open WhatsApp
      window.open(url, "_blank");

      // Reset form
      this.form = {
        name: "",
        email: "",
        subject: "",
        message: "",
      };

      this.submitMessage = "WhatsApp opened. Please hit Send!";
      this.submitStatus = "success";
      this.isSubmitting = false;

      setTimeout(() => {
        this.submitMessage = "";
      }, 5000);
    },
  },
};
</script>

<style scoped>
.contact-form {
  background: var(--glass-bg);
  backdrop-filter: blur(20px);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  padding: 3rem;
}

.form-title {
  font-size: 2rem;
  margin-bottom: 2rem;
  color: white;
}

.form-group {
  margin-bottom: 2rem;
  text-align: left;
}

.form-input {
  width: 100%;
  padding: 1rem;
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 10px;
  background: rgba(255, 255, 255, 0.1);
  color: white;
  font-size: 1rem;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}

.form-input:focus {
  outline: none;
  border-color: rgba(255, 255, 255, 0.6);
  background: rgba(255, 255, 255, 0.2);
}

.form-input::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.form-textarea {
  min-height: 120px;
  resize: vertical;
}

.submit-btn {
  background: var(--accent-gradient);
  color: white;
  padding: 1rem 3rem;
  border: none;
  border-radius: 50px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.3s ease;
  width: 100%;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.submit-message {
  margin-top: 1rem;
  padding: 1rem;
  border-radius: 10px;
  font-weight: 500;
}

.submit-message.success {
  background: rgba(39, 202, 63, 0.2);
  color: #27ca3f;
  border: 1px solid rgba(39, 202, 63, 0.3);
}

.submit-message.error {
  background: rgba(255, 95, 86, 0.2);
  color: #ff5f56;
  border: 1px solid rgba(255, 95, 86, 0.3);
}
</style>
