<script setup>
import Logo from "~/assets/Logo.svg";
</script>

<template lang='pug'>
.header
  a(href="/")
    img(:src="Logo")
</template>
<style scoped lang='scss'>
.header {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 85px;
}
</style>
