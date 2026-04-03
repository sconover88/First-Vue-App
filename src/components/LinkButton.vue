<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    variant="flat"
    color="surface-variant"
    block
    size="large"
    class="text-none link-btn"
    rounded="lg"
  >
    <div class="link-btn-content">
      <v-icon size="20" class="link-btn-icon">{{ icon }}</v-icon>
      <span>{{ label }}</span>
    </div>
  </v-btn>
</template>

<style scoped>
.link-btn :deep(.v-btn__content) {
  width: 100%;
}

.link-btn-content {
  display: flex;
  align-items: center;
  width: 100%;
  padding-left: 33%;
}

.link-btn-icon {
  width: 24px;
  margin-right: 12px;
  flex-shrink: 0;
}
</style>
