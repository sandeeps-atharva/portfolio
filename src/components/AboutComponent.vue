<template>
  <section id="about" class="about">
    <div class="about-container">
      <div class="about-content">
        <div class="title-wrapper">
          <h2>{{ title }}</h2>
          <div class="title-decoration"></div>
        </div>

        <div class="text-content">
          <p class="intro-text">{{ text }}</p>

          <div class="highlight-stats">
            <div class="stat-item">
              <span class="stat-number">3+</span>
              <span class="stat-label">Years Experience</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">50+</span>
              <span class="stat-label">Projects Completed</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">10+</span>
              <span class="stat-label">Technologies</span>
            </div>
          </div>

          <div class="personality-traits">
            <span class="trait">Problem Solver</span>
            <span class="trait">Tech Enthusiast</span>
            <span class="trait">Clean Code Advocate</span>
            <span class="trait">Continuous Learner</span>
          </div>
        </div>
      </div>

      <div class="about-visual">
        <div class="code-snippet">
          <div class="code-header">
            <div class="code-dots">
              <span class="dot red"></span>
              <span class="dot yellow"></span>
              <span class="dot green"></span>
            </div>
            <span class="file-name">developer.js</span>
          </div>
          <div class="code-content">
            <div class="code-line">
              <span class="keyword">const</span>
              <span class="variable">developer</span>
              <span class="operator">=</span>
              <span class="punctuation">{</span>
            </div>
            <div class="code-line">
              &nbsp;&nbsp;<span class="property">name</span
              ><span class="punctuation">:</span>
              <span class="string">'Sandeep'</span
              ><span class="punctuation">,</span>
            </div>
            <div class="code-line">
              &nbsp;&nbsp;<span class="property">role</span
              ><span class="punctuation">:</span>
              <span class="string">'Full Stack Developer'</span
              ><span class="punctuation">,</span>
            </div>
            <div class="code-line">
              &nbsp;&nbsp;<span class="property">passion</span
              ><span class="punctuation">:</span>
              <span class="string">'Creating awesome web experiences'</span
              ><span class="punctuation">,</span>
            </div>
            <div class="code-line">
              &nbsp;&nbsp;<span class="property">coffee</span
              ><span class="punctuation">:</span>
              <span class="boolean">true</span>
            </div>
            <div class="code-line">
              <span class="punctuation">};</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: "About Me",
      text: "Hey, I'm Sandeep — a full-stack developer who lives and breathes code! I've got solid skills in HTML, CSS, JavaScript, React, Next.js, React Native, Vue.js, Node.js, and Express. I also worked as a frontend dev on Shopify app projects, building clean, responsive UI. I love solving real-world problems, geeking out over new tech, and making the web a cooler, smoother, and way more awesome place. 🚀💻",
    };
  },
};
</script>

<style scoped>
.about {
  padding: 80px 20px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  position: relative;
  overflow: hidden;
}

.about::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(
      circle at 20% 80%,
      rgba(120, 119, 198, 0.3) 0%,
      transparent 50%
    ),
    radial-gradient(
      circle at 80% 20%,
      rgba(255, 255, 255, 0.1) 0%,
      transparent 50%
    );
  pointer-events: none;
}

.about-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 1;
}

.title-wrapper {
  text-align: center;
  margin-bottom: 2rem;
}

.title-wrapper h2 {
  font-size: 3rem;
  font-weight: 700;
  margin: 0;
  background: linear-gradient(45deg, #ffffff, #f8f9ff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.title-decoration {
  width: 80px;
  height: 4px;
  background: linear-gradient(45deg, #ff6b6b, #feca57);
  margin: 1rem auto;
  border-radius: 2px;
}

.intro-text {
  font-size: 1.2rem;
  line-height: 1.8;
  margin-bottom: 2.5rem;
  color: rgba(255, 255, 255, 0.9);
}

.highlight-stats {
  display: flex;
  justify-content: space-around;
  margin: 2.5rem 0;
  padding: 2rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.stat-item {
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: #feca57;
}

.stat-label {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.8);
  font-weight: 500;
}

.personality-traits {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  margin-top: 2rem;
}

.trait {
  background: rgba(255, 255, 255, 0.2);
  padding: 0.6rem 1.2rem;
  border-radius: 25px;
  font-size: 0.9rem;
  font-weight: 500;
  border: 1px solid rgba(255, 255, 255, 0.3);
  transition: all 0.3s ease;
}

.trait:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.about-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.code-snippet {
  background: #1e1e1e;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  max-width: 400px;
  width: 100%;
  transform: rotate(-2deg);
  transition: transform 0.3s ease;
}

.code-snippet:hover {
  transform: rotate(0deg) scale(1.05);
}

.code-header {
  background: #2d2d2d;
  padding: 1rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.code-dots {
  display: flex;
  gap: 0.5rem;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.dot.red {
  background: #ff5f56;
}
.dot.yellow {
  background: #ffbd2e;
}
.dot.green {
  background: #27ca3f;
}

.file-name {
  color: #ffffff;
  font-size: 0.9rem;
  font-family: "Monaco", "Menlo", "Ubuntu Mono", monospace;
}

.code-content {
  padding: 1.5rem;
  font-family: "Monaco", "Menlo", "Ubuntu Mono", monospace;
  font-size: 0.9rem;
  line-height: 1.6;
}

.code-line {
  margin-bottom: 0.5rem;
}

.keyword {
  color: #c586c0;
}
.variable {
  color: #9cdcfe;
}
.operator {
  color: #d4d4d4;
}
.property {
  color: #92c5f7;
}
.string {
  color: #ce9178;
}
.boolean {
  color: #569cd6;
}
.punctuation {
  color: #d4d4d4;
}

/* Responsive Design */
@media (max-width: 968px) {
  .about-container {
    grid-template-columns: 1fr;
    gap: 3rem;
    text-align: center;
  }

  .title-wrapper h2 {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .about {
    padding: 60px 15px;
  }

  .title-wrapper h2 {
    font-size: 2rem;
  }

  .intro-text {
    font-size: 1.1rem;
  }

  .highlight-stats {
    flex-direction: column;
    gap: 1.5rem;
    padding: 1.5rem;
  }

  .stat-item {
    flex-direction: row;
    justify-content: center;
    gap: 1rem;
  }

  .stat-number {
    font-size: 2rem;
  }

  .personality-traits {
    gap: 0.75rem;
  }

  .trait {
    font-size: 0.8rem;
    padding: 0.5rem 1rem;
  }
}

@media (max-width: 480px) {
  .about {
    padding: 40px 10px;
  }

  .code-snippet {
    max-width: 100%;
    transform: none;
  }

  .code-snippet:hover {
    transform: scale(1.02);
  }

  .code-content {
    padding: 1rem;
    font-size: 0.8rem;
  }
}
</style>
