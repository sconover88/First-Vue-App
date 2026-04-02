<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="about-page">
    <div class="card">
      <RouterLink to="/" class="back-link">← Back</RouterLink>
      <h1>About Me</h1>
      <p>
        Hi, I'm Scott Conover — a designer and developer who loves building
        clean, thoughtful digital experiences. I'm passionate about crafting
        interfaces that feel effortless and look great.
      </p>
      <p>
        When I'm not pushing pixels or writing code, you'll find me exploring
        new tools, tinkering with side projects, or grabbing a good cup of
        coffee.
      </p>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 480px;
  margin: 0 auto;
}

.card {
  background: var(--card-bg);
  border-radius: var(--radius);
  padding: 2.5rem 2rem;
  width: 100%;
  transition: background-color var(--transition);
}

h1 {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

p {
  color: var(--text-muted);
  line-height: 1.7;
  margin-bottom: 1rem;
}

p:last-child {
  margin-bottom: 0;
}

.back-link {
  display: inline-block;
  color: var(--text-muted);
  text-decoration: none;
  font-size: 0.9rem;
  margin-bottom: 1.5rem;
  transition: color var(--transition);
}

.back-link:hover {
  color: var(--text);
}
</style>
