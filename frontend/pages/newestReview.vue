<script setup lang="ts">
  import { Review } from '~/types/review';
  const router = useRouter()
  const { data: reviews } = await useFetch<Review[]>(
    'http://localhost:8000/api/newestReview',
    {}
  )
</script>

<template>
  <div>
    <h1>最新のレビューTOP50</h1>

    <ul>
      <li v-for="review in reviews" :key="review.id">
        <NuxtLink :to="'/reviewDetail/' + review.id"
          >{{ review.book_id }} - {{ review.id }}</NuxtLink
        >
      </li>
    </ul>

    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
