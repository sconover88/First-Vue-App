<script setup lang="ts">
import { computed } from 'vue'
import { useTheme } from 'vuetify'
import profilePhoto from '@/assets/picture-of-me.JPG'
import LinkButton from '@/components/LinkButton.vue'

const theme = useTheme()
const isDark = computed(() => theme.global.name.value === 'dark')

function toggleTheme() {
  theme.global.name.value = isDark.value ? 'light' : 'dark'
}

const links = [
  { label: 'Portfolio', url: 'https://example.com', icon: 'mdi-palette' },
  { label: 'Dribbble', url: 'https://dribbble.com', icon: 'mdi-basketball' },
  { label: 'LinkedIn', url: 'https://linkedin.com', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: 'mdi-email-outline' },
]
</script>

<template>
  <v-container class="d-flex align-center justify-center fill-height">
    <v-row justify="center">
      <v-col cols="12" sm="8" md="6" lg="5" style="max-width: 480px">
        <div class="d-flex justify-end mb-4">
          <v-btn
            icon
            variant="outlined"
            size="small"
            @click="toggleTheme"
            :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
          >
            <v-icon>{{ isDark ? 'mdi-weather-sunny' : 'mdi-weather-night' }}</v-icon>
          </v-btn>
        </div>

        <v-card class="pa-8 text-center" rounded="lg" elevation="4">
          <v-avatar size="96" class="mb-4">
            <v-img :src="profilePhoto" alt="Scott Conover" cover />
          </v-avatar>

          <h1 class="text-h5 font-weight-bold">Scott Conover</h1>
          <p class="text-body-2 text-medium-emphasis mb-8">Designer &amp; Developer</p>

          <div class="d-flex flex-column ga-4">
            <LinkButton
              v-for="link in links"
              :key="link.label"
              :label="link.label"
              :url="link.url"
              :icon="link.icon"
            />

            <v-btn
              to="/about"
              variant="flat"
              color="surface-variant"
              block
              size="large"
              class="text-none about-btn"
              rounded="lg"
            >
              <div class="about-btn-content">
                <v-icon size="20" class="about-btn-icon">mdi-account</v-icon>
                <span>About Me</span>
              </div>
            </v-btn>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.about-btn :deep(.v-btn__content) {
  width: 100%;
}

.about-btn-content {
  display: flex;
  align-items: center;
  width: 100%;
  padding-left: 33%;
}

.about-btn-icon {
  width: 24px;
  margin-right: 12px;
  flex-shrink: 0;
}
</style>
