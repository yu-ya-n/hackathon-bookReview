<script setup lang="ts">
  import { Book } from '~/types/book';
  const router = useRouter()
  const { data: books } = await useFetch<Book[]>(
    'http://localhost:8000/api/books',
    {}
  )
</script>

<template>
  <div>
    <h1>書籍一覧</h1>
    <NuxtLink to="/bookDetail/1">１番目の本</NuxtLink>
    <ul>
      <li v-for="book in books" :key="book.id">
        <NuxtLink :to="'/bookDetail/' + book.id">{{ book.name }}</NuxtLink>
      </li>
    </ul>
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
