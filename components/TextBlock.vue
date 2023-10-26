<script setup>
defineProps(["data"]);
</script>

<template lang='pug'>
.text-block
  .article-top-part
    div(v-html="data")
</template>

<style lang='scss'>
.text-block {
  max-width: min(calc(100% - 20px), 884px);
  margin: auto;
  margin-bottom: 80px;
  blockquote {
    color: var(--Gray, #8d959c);
  }
}
</style>
