<script setup lang="ts">
  import { Book } from '~/types/book';
  const { data: books } = await useFetch<Book[]>(
    'http://localhost:8000/api/books',
    {}
  )
</script>

<template>
  <div>
    <h1>書籍一覧</h1>
    <v-list lines="two">
      <v-list-item
        v-for="book in books"
        :key="book.id"
        :title="book.name"
        :subtitle="book.detail"
        :to="'/bookDetail/' + book.id"
        nuxt
      ></v-list-item>
    </v-list>
    <br />
    <BackButton />
  </div>
</template>
