<script setup lang="ts">
  import { Book } from '~/types/book';
  const route = useRoute()
  const router = useRouter()
  const { data } = await useFetch<Book>(
    'http://localhost:8000/api/books/' + route.params.id,
    {}
  )
</script>

<template>
  <div>
    <h1>書籍詳細</h1>
    題名：{{ data?.name }}
    <br />
    著者：{{ data?.author }}
    <br />
    内容：{{ data?.detail }}
    <br />
    価格：{{ data?.price }}円
    <br />
    <!-- TODO: 日付の表示をかっこよくする -->
    発行日：{{ data?.published_at }}
    <br />
    <br />
    <textarea></textarea>
    <br />
    <input type="button" value="レビューを投稿する！" />
    <br />
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
