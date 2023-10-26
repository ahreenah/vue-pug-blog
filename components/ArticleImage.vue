<script setup>
defineProps(["data"]);
</script>

<template lang='pug'>
.article-image
  img(:src="data.src")
  .article-image-description
    | {{ data.caption }}
</template>

<style scoped lang='scss'>
.article-image {
  margin-bottom: 100px;
  margin-left: 10px;
  margin-right: 10px;
  display: flex;
  flex-direction: column;
  img {
    margin-bottom: 15px;
    border-radius: 2px 220px 2px 2px;
  }
  .article-image-description {
    text-align: right;
  }
}
</style>
