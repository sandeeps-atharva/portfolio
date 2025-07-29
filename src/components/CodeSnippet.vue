<template>
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
      <div v-for="(line, index) in codeLines" :key="index" v-html="line"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CodeSnippet",
  data() {
    return {
      codeLines: [
        "const developer = {",
        "&nbsp;&nbsp;name: 'Sandeep Suthar',",
        "&nbsp;&nbsp;role: 'Frontend Developer',",
        "&nbsp;&nbsp;location: 'Ahmedabad, Gujarat',",
        "&nbsp;&nbsp;passion: 'Creating amazing UX',",
        "&nbsp;&nbsp;coffee: true,",
        "&nbsp;&nbsp;code: 'clean & scalable'",
        "};",
      ],
    };
  },
};
</script>

<style scoped>
.code-snippet {
  background: #1e1e1e;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: var(--shadow-heavy);
  transform: rotate(-2deg);
  transition: transform 0.3s ease;
}

.code-snippet:hover {
  transform: rotate(0deg) scale(1.02);
}

.code-header {
  background: #2d2d2d;
  padding: 1rem 1.5rem;
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
  color: white;
  font-family: "Monaco", monospace;
  font-size: 0.9rem;
}

.code-content {
  padding: 2rem;
  font-family: "Monaco", monospace;
  font-size: 0.9rem;
  line-height: 1.6;
  color: #d4d4d4;
}

@media (max-width: 768px) {
  .code-snippet {
    transform: none;
  }
}
</style>
