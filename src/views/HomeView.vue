<script setup lang="ts">
import LinkCard from '@/components/LinkCard.vue'
import ThemeToggle from '@/components/ThemeToggle.vue'

const links = [
  { label: 'Portfolio', url: 'https://example.com', icon: '🎨' },
  { label: 'Dribbble', url: 'https://dribbble.com', icon: '🏀' },
  { label: 'LinkedIn', url: 'https://linkedin.com', icon: '💼' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: '✉️' },
]
</script>

<template>
  <div class="bio-page">
    <ThemeToggle />
    <div class="card">
      <div class="avatar">
        <span class="avatar-placeholder">SC</span>
      </div>
      <h1 class="name">Scott Conover</h1>
      <p class="tagline">Designer &amp; Developer</p>
      <div class="links">
        <LinkCard
          v-for="link in links"
          :key="link.label"
          :label="link.label"
          :url="link.url"
          :icon="link.icon"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
.bio-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 480px;
  margin: 0 auto;
  position: relative;
}

.card {
  background: var(--card-bg);
  border-radius: var(--radius);
  padding: 2.5rem 2rem;
  width: 100%;
  text-align: center;
  transition: background-color var(--transition);
}

.avatar {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  background: var(--btn-bg);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.25rem;
  overflow: hidden;
  border: 3px solid var(--btn-border);
  transition: background-color var(--transition), border-color var(--transition);
}

.avatar-placeholder {
  font-size: 2rem;
  font-weight: 700;
  color: var(--text-muted);
}

.name {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 0.25rem;
}

.tagline {
  color: var(--text-muted);
  font-size: 0.95rem;
  margin-bottom: 2rem;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}
</style>
