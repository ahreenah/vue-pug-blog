<template lang='pug'>
.subscribe-form
  h3 Подпишись на расылку
  input(placeholder="Email")
  button
    | Подписаться
</template>

<style scoped lang='scss'>
.subscribe-form {
  background: black;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  padding: 20px 30px;
  gap: 37px;
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
  button {
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
