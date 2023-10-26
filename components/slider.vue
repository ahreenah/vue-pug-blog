<script setup>
import Left from "~/assets/left.svg";
import Right from "~/assets/right.svg";
let props = defineProps(["images"]);
let index = ref(0);
const nextImage = () => (index.value = (index.value + 1) % props.images.length);
const prevImage = () =>
  (index.value =
    (props.images.length + (index.value - 1)) % props.images.length);
</script>

<template lang="pug">
.slider
  .slider--contents
    img(:src="Left", @click="prevImage")
    .images
      img(:src="images[index]")
    img(:src="Right", @click="nextImage")
  .slider--counter
    | {{ index + 1 }} / {{ images.length }}
</template>

<style scoped lang='scss'>
.slider {
  margin-bottom: 100px;
  img {
    max-width: 100%;
  }
  .images {
    display: flex;
  }
  &--contents {
    display: flex;
    justify-content: space-between;
  }
  &--counter {
    text-align: center;
    margin-top: 10px;
  }
}
</style>
