<script setup>
  defineProps(['data'])
</script>

<template lang='pug'>
.article-intro
  .img-wrapper(:style="{ backgroundImage: `url(${data.image})` }")
  .article-top-part
    h1 {{ data.title }}
    .stat {{ data.reading_time }} мин время прочтения
    .stat {{ data.views_count }} прочитали статью
    .article--description {{ data.short_description }}
</template>

<style scoped lang='scss'>
$gray: #8d959c;
.article-intro {
  margin-bottom: 100px;
  display: flex;
  margin-left:10px;
  margin-right:10px;
  gap: 31px;
  align-items: center;
  h1 {
    font-family: Montserrat;
    font-size: 56px;
    font-style: normal;
    font-weight: 800;
    line-height: 66px; /* 117.857% */
  }
  .img-wrapper {
    height: 580px;
    flex-basis: 541px;
    flex-shrink: 0;
    border-top-right-radius: 220px;
    background-position: center;
    background-size: cover;
    width: 200px;
    @media(max-width:1024px){
      display:none
    }
  }
  .stat {
    color: $gray;
  }
  .article--description {
    margin-top: 50px;
  }
}
</style>
