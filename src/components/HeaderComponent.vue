<template>
  <header class="header">
    <div class="logo">SanDev</div>

    <!-- Burger Menu Button (visible only on small screens) -->
    <button class="menu-btn" @click="toggleMenu">☰</button>

    <!-- Navigation Menu -->
    <nav :class="{ open: isMenuOpen }">
      <ul>
        <li v-for="item in menuItems" :key="item.id">
          <a @click="scrollToContact(item.ids)">{{ item.label }}</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",

  data() {
    return {
      isMenuOpen: false,
      menuItems: [
        { id: 1, label: "Home", href: "#hero", ids: "home" },
        { id: 2, label: "About", href: "#about", ids: "about" },
        { id: 3, label: "Skills", href: "#skills", ids: "skill" },
        { id: 4, label: "Projects", href: "#projects", ids: "project" },
        { id: 5, label: "Contact", href: "#contact", ids: "contact" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },

    scrollToContact(x) {
      document.getElementById(`${x}`).scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #42b983;
  padding: 20px;
  color: white;
  position: sticky;
  top: 0;
  z-index: 100;
}

.logo {
  font-weight: bold;
  font-size: 1.5em;
}

/* Burger Button */
.menu-btn {
  display: none;
  background: none;
  border: none;
  color: white;
  font-size: 26px;
  cursor: pointer;
}

/* Nav styles */
nav ul {
  list-style: none;
  display: flex;
  gap: 16px;
  padding: 0;
  margin: 0;
}

nav a {
  color: white;
  text-decoration: none;
}

nav a:hover {
  text-decoration: underline;
}

/* Responsive for Mobile */
@media (max-width: 768px) {
  .menu-btn {
    display: block;
  }

  nav {
    position: absolute;
    top: 70px;
    right: 20px;
    background: #2d9062;
    border-radius: 8px;
    padding: 10px;
    display: none;
    flex-direction: column;
  }

  nav.open {
    display: flex;
  }

  nav ul {
    flex-direction: column;
    gap: 10px;
  }
}
</style>
