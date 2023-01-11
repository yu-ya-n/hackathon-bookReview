<script setup lang="ts">
  const router = useRouter()
</script>

<template>
  <v-btn
    class="mt-10"
    color="primary"
    prepend-icon="mdi-arrow-left"
    nuxt
    @click="router.back()"
  >
    戻る
  </v-btn>
</template>
