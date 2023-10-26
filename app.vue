<script setup>
import Slider from "./components/slider.vue";
import ArticleList from "./components/ArticleList.vue";
import Logo from "~/assets/Logo.svg";
import Footer from "./components/footer.vue";
import CtaForm from "./components/CtaForm.vue";
import SubscribeForm from "./components/SubscribeForm.vue";
import TextBlock from "./components/TextBlock.vue";
import Header from "./components/Header.vue";

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
Header
.page-content
  div(v-for="item in data.body", :key="item")
    ArticleIntro(v-if="item.type == 'article_intro_block'", :data="item.data")
    TextBlock(v-if="item.type == 'text_block'", :data="item.data")
    ArticleImage(v-if="item.type == 'image_block'", :data="item.data")
    SubscribeForm(v-if="item.type == 'subscribe_form_block'")
    ArticleList(v-if="item.type == 'article_list_block'", :data="item.data")
    CtaForm(v-if="item.type == 'cta_form_block'")
    Slider(:images="item.data", v-if="item.type == 'slider_block'")

Footer
</template>

<style lang='scss'>
body {
  margin: 0;
  color: var(--Text, #1B1B1B);
}
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;1,800&display=swap");
* {
  font-family: Montserrat;
}
.page-content {
  max-width: 1340px;
  margin: auto;
}
</style>
