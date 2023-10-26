<script setup>
import CtaImage from "~/assets/cta-image.png";
</script>

<template lang='pug'>
.cta-form-block
  img(:src="CtaImage")
  form
    h3 Стань участником проекта
    input(placeholder="Имя")
    input(placeholder="Телефон")
    input(placeholder="Email")
    button
      | Присоединиться
</template>

<style scoped lang='scss'>
.cta-form-block {
  padding: 60px;
  background: black;
  display: flex;
  align-items: center;
  padding-left: 30px;
  padding-right: 30px;
  gap: 37px;
  img {
    flex-grow: 1;
    height: 100%;
    @media screen and (max-width:1024px){
      display:none;
    }
  }
  h3 {
    color: white;
    margin-right: auto;
  }
  input {
    background: transparent;
    height: 46px;
    border: none;
    border-bottom: 1px solid #8d959c;
  }
  form {
    display: flex;
    flex-grow: 1;
    gap: 25px;
    flex-direction: column;
  }
  button {
    width: fit-content;
    color: white;
    border: none;
    border-radius: 2px;
    background: var(--Blue, #3657d3);
    display: inline-flex;
    padding: 10px 50px;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }
}
</style>
