<script setup>
  const router = useRouter()
</script>

<template>
  <div>
    <h1>書籍一覧</h1>
    <br />
    <ul>
      <li><NuxtLink to="bookDetail/1">書籍1</NuxtLink></li>
      <li><NuxtLink to="bookDetail/2">書籍2</NuxtLink></li>
      <li><NuxtLink to="bookDetail/3">書籍3</NuxtLink></li>
    </ul>
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
