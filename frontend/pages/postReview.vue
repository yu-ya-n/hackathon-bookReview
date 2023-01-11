<script setup>
  const router = useRouter()
</script>

<template>
  <div>
    <h1>レビュー投稿</h1>
    この本
    <br />
    <br />
    レビュー内容
    <br />
    <textarea></textarea>
    <br />
    <input type="button" value="投稿する！" />
    <br />
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
