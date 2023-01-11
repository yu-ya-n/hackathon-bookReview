<script setup>
  const route = useRoute()
  const router = useRouter()
</script>

<template>
  <div>
    <h1>書籍詳細</h1>
    本：{{ route.params.id }}
    <br />
    <br />
    こんな本です。
    <br />
    <br />
    <NuxtLink to="/postReview">レビューを投稿する</NuxtLink>
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
