<script setup lang="ts">
  import { Book } from '~/types/book';
  const route = useRoute()
  const rating = ref(0)
  const { data } = await useFetch<Book>(
    'http://localhost:8000/api/books/' + route.params.id,
    {}
  )

  const postData = { book_id: 1, review: 'abcdefg' }

  const { response } = await useFetch('http://localhost:8000/api/reviews/', {
    method: 'POST',
    body: postData
  })
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
    <v-textarea auto-grow></v-textarea>
    <v-rating v-model="rating" color="blue" size="30"></v-rating>
    <br />
    <v-btn class="mt-10" color="yellow" prepend-icon="mdi-send" nuxt>
      レビューを投稿する！
    </v-btn>
    <br />
    <BackButton />
  </div>
</template>
