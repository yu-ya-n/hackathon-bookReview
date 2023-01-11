<script setup lang="ts">
  const theme = ref('light')

  function onClick() {
    theme.value = theme.value === 'light' ? 'dark' : 'light'
  }
</script>

<template>
  <v-app :theme="theme">
    <v-app-bar>
      <v-app-bar-title> <h3>僕の考えた最強の書評サイト</h3></v-app-bar-title>
      <v-spacer></v-spacer>
      <v-btn
        :prepend-icon="
          theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'
        "
        @click="onClick"
      ></v-btn>
    </v-app-bar>
    <v-main class="mx-auto">
      <v-container>
        <NuxtLoadingIndicator />
        <NuxtPage />
      </v-container>
    </v-main>
  </v-app>
</template>
