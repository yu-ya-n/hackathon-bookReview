<script setup lang="ts">
  import { Review } from '~/types/review';
  const route = useRoute()
  const router = useRouter()
  const { data } = await useFetch<Review>(
    'http://localhost:8000/api/reviews/' + route.params.id,
    {}
  )
</script>

<!-- TODO: ポップアップで見せる？ -->
<template>
  <div>
    <h1>書籍詳細</h1>
    レビュー：{{ data?.review }}
    <br />
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
