<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <v-app>
    <v-main class="app-bg">
      <div class="flare flare-1"></div>
      <div class="flare flare-2"></div>
      <div class="flare flare-3"></div>
      <div class="flare flare-4"></div>
      <div class="flare flare-5"></div>
      <RouterView />
    </v-main>
  </v-app>
</template>

<style scoped>
.app-bg {
  position: relative;
  overflow: hidden;
}

.flare {
  position: fixed;
  border-radius: 50%;
  pointer-events: none;
  z-index: 0;
  filter: blur(120px);
}

/* Dark mode flares */
.flare-1 {
  width: 550px;
  height: 550px;
  background: radial-gradient(circle, rgba(139, 92, 246, 0.35), transparent 70%);
  top: -80px;
  right: -60px;
}

.flare-2 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, rgba(59, 130, 246, 0.3), transparent 70%);
  bottom: -60px;
  left: -40px;
}

.flare-3 {
  width: 450px;
  height: 450px;
  background: radial-gradient(circle, rgba(168, 85, 247, 0.25), transparent 70%);
  top: 40%;
  left: -80px;
}

.flare-4 {
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(99, 102, 241, 0.28), transparent 70%);
  bottom: 20%;
  right: -50px;
}

.flare-5 {
  width: 350px;
  height: 350px;
  background: radial-gradient(circle, rgba(79, 70, 229, 0.2), transparent 70%);
  top: 15%;
  left: 50%;
}
</style>

<style>
/* Light mode — unscoped so .v-theme--light selector works */
.v-theme--light .flare-1 {
  background: radial-gradient(circle, rgba(139, 92, 246, 0.6), transparent 70%) !important;
}

.v-theme--light .flare-2 {
  background: radial-gradient(circle, rgba(59, 130, 246, 0.55), transparent 70%) !important;
}

.v-theme--light .flare-3 {
  background: radial-gradient(circle, rgba(168, 85, 247, 0.5), transparent 70%) !important;
}

.v-theme--light .flare-4 {
  background: radial-gradient(circle, rgba(99, 102, 241, 0.55), transparent 70%) !important;
}

.v-theme--light .flare-5 {
  background: radial-gradient(circle, rgba(79, 70, 229, 0.45), transparent 70%) !important;
}
</style>
