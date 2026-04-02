<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <a :href="url" target="_blank" rel="noopener noreferrer" class="link-btn">
    <span class="link-icon">{{ icon }}</span>
    <span class="link-label">{{ label }}</span>
  </a>
</template>

<style scoped>
.link-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  padding: 0.875rem 1.25rem;
  background: var(--btn-bg);
  border: 1px solid var(--btn-border);
  border-radius: var(--radius);
  color: var(--text);
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  transition:
    background-color var(--transition),
    border-color var(--transition),
    transform 0.2s ease,
    box-shadow 0.2s ease;
  cursor: pointer;
}

.link-btn:hover {
  background: var(--btn-hover);
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

.link-btn:active {
  transform: translateY(0);
  box-shadow: none;
}

.link-icon {
  font-size: 1.15rem;
}

.link-label {
  font-weight: 500;
}
</style>
