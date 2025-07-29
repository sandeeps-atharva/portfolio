<template>
  <header class="header">
    <div class="nav-container">
      <div class="logo">SanDev</div>
      <nav>
        <ul class="nav-menu" :class="{ active: isMenuOpen }">
          <li v-for="(link, index) in navLinks" :key="index">
            <a
              href="javascript:void(0)"
              class="nav-link"
              @click="scrollToSection(link.target)"
            >
              {{ link.text }}
            </a>
          </li>
        </ul>
      </nav>
      <button class="menu-toggle" @click="toggleMenu">☰</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      isMenuOpen: false,
      navLinks: [
        { text: "Home", target: "hero" },
        { text: "About", target: "about" },
        { text: "Skills", target: "skills" },
        { text: "Experience", target: "experience" },
        { text: "Projects", target: "projects" },
        { text: "Contact", target: "contact" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
    scrollToSection(id) {
      const section = document.getElementById(id);
      if (section) {
        section.scrollIntoView({ behavior: "smooth", block: "start" });
        this.closeMenu(); // close menu on mobile after click
      }
    },
  },
};
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--glass-border);
  padding: 1rem 0;
  transition: all 0.3s ease;
}
.nav-menu.active {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 70px; /* adjust based on your header height */
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  width: 100%;
  padding: 1rem;
  gap: 1.5rem;
  z-index: 999;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
}

.logo {
  font-size: 1.8rem;
  font-weight: 800;
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav-link {
  color: var(--text-primary);
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link::after {
  content: "";
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--primary-gradient);
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
}

@media (max-width: 968px) {
  .nav-menu {
    display: none;
  }

  .menu-toggle {
    display: block;
  }

  .nav-container {
    padding: 0 1rem;
  }
}
</style>
