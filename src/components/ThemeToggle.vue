<script setup lang="ts">
import { ref, onMounted } from 'vue'

const isLight = ref(false)

function toggle() {
  isLight.value = !isLight.value
  document.documentElement.classList.toggle('light', isLight.value)
}

onMounted(() => {
  document.documentElement.classList.remove('light')
})
</script>

<template>
  <button class="theme-toggle" @click="toggle" :aria-label="isLight ? 'Switch to dark mode' : 'Switch to light mode'">
    {{ isLight ? '🌙' : '☀️' }}
  </button>
</template>

<style scoped>
.theme-toggle {
  position: absolute;
  top: -0.5rem;
  right: 0;
  background: var(--btn-bg);
  border: 1px solid var(--btn-border);
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  cursor: pointer;
  transition:
    background-color var(--transition),
    border-color var(--transition),
    transform 0.2s ease;
  color: var(--text);
}

.theme-toggle:hover {
  background: var(--btn-hover);
  transform: scale(1.1);
}
</style>
