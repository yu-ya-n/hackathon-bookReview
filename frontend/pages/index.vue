<script setup lang="ts"></script>

<template>
  <div>
    <v-btn
      class="mt-10"
      color="primary"
      prepend-icon="mdi-book"
      to="/bookList"
      nuxt
    >
      書籍一覧
    </v-btn>
    <br />
    <v-btn
      class="mt-10"
      prepend-icon="mdi-star"
      color="yellow"
      to="/newestReview"
      nuxt
    >
      最新レビューTOP50！
    </v-btn>
  </div>
</template>
