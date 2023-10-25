<script setup>
const route = useRoute();
console.log("current name", route.fullpath, route.path);
const {
  data,
  pending,
  status: s,
} = useFetch("http://devtwit8.ru/api/v1/page/?path=" + route.path);

watch(data, console.log);
console.log("data", data);

const items = ref([{ type: "link", url: "", title: "aaaaa" }]);
</script>
<template lang='pug'>
.page-content
  div(v-for="item in data.body", :key="item")
    div(:key="item") 
      h2 {{ item.data.title }}
      .articles
        .article(v-for="article in item.data.articles", :key="article")
          .img-wrapper(:style="{ background: `url(${article.image})` }")
          h3.article--title {{ article.title }}
          a(:href="article.link") читать
</template>

<style lang='scss'>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;1,800&display=swap");
* {
  font-family: Montserrat;
}
.page-content {
  max-width: 1340px;
  margin: auto;
}
.articles {
  display: flex;
  //  grid-template-columns: 1fr 1fr 1fr;
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
</style>
