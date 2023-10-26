<script setup>
import Logo from "~/assets/Logo.svg";

import FacebookLogo from "~/assets/facebook.svg";
import VkLogo from "~/assets/vk.svg";
import InstagramLogo from "~/assets/instagram.svg";
import TelegramLogo from "~/assets/telegram.svg";
</script>

<template lang='pug'>
.footer
  .footer-contents
    .footer-description
      img(:src="Logo")
      p Cтатьи о дизайне и искусстве, которые исследуют творческие вдохновения и актуальные тенденции, раскрывая мир эстетики и креативности
    .footer-contacts
      .footer-contacts-label email
      .footer-contacts-email testblogsupport@gmail.com
      .footer-social-links
        img(:src="FacebookLogo")
        img(:src="VkLogo")
        img(:src="InstagramLogo")
        img(:src="TelegramLogo")
  SubscribeForm
</template>

<style scoped lang='scss'>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;1,800&family=Ubuntu:ital@1&display=swap");
.footer {
  padding-top: 50px;
  margin-top: 200px;
  .footer-contents {
    padding-left: 10px;
    padding-right: 10px;
    margin: auto;
    max-width: 1340px;
    margin-bottom: 70px;
    display: flex;
    justify-content: space-between;
    .footer-description {
      max-width: 426px;
    }
  }
  .subscribe-form {
    max-width: 1340px;
    margin: auto;
  }
  &-contacts {
    display: flex;
    flex-direction: column;
    .footer-social-links {
      display: flex;
      gap: 20px;
      margin-top: 24px;
    }
    &-label {
      color: var(--Gray, #8d959c);
    }
    &-email {
      color: var(--Text, #1b1b1b);
      /* Body 2 */
      font-family: Ubuntu;
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: 22px; /* 122.222% */
    }
  }
}
</style>
