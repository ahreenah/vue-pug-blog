<script setup>
defineProps(["data", "articles", "title"]);
</script>

<template lang='pug'>
.article-list-block 
  h2 {{ data.title }}
  .articles
    .article(v-for="article in data?.articles", :key="article")
      .img-wrapper(:style="{ backgroundImage: `url(${article.image})` }")
      h3.article--title {{ article.title }}
      a(:href="article.link") читать
</template>

<style lang='scss'>
.article-list-block {
  .articles {
    margin-left: 10px;
    margin-right: 10px;
    margin-bottom: 100px;
    display: flex;
    flex-wrap: wrap;
    flex-wrap: wrap;
    grid-gap: 20px;
    .article {
      flex-basis: 32%;
      flex-grow: 1;
      flex-shrink: 0;
      display: flex;
      flex-direction: column;
      .img-wrapper {
        height: 240px;
        background-position: center;
        background-size: cover;
      }
      .article--title {
        margin-top: 20px;
        flex-grow: 1;
        margin-bottom: 30px;
        font-family: Montserrat;
        font-size: 22px;
        font-style: normal;
        font-weight: 800;
        line-height: 30px; /* 136.364% */
      }
      img {
        width: 100%;
      }
      a {
        display: block;
        text-decoration: none;
        padding: 10px 50px;
        width: fit-content;
        background: black;
        color: white;
      }
    }
  }
}
</style>
