<script setup>
  const router = useRouter()
</script>

<template>
  <div>
    <h1>最新のレビューTOP50</h1>
    <input type="button" value="戻る" @click="router.back()" />
  </div>
</template>
