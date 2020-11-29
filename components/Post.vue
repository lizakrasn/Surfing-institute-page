<template lang="pug">
  .post
    .post__image-container
      img(v-bind:src="imageUrl" alt="surfer").post__image
    .post__info
      p.post__title {{title}}
      p.post__text {{text}}
      button(type="button").post__button Read More
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "Post",
  props: ["imageUrl", "title", "text"]
})
</script>

<style lang="sass" scoped>
  .post
    display: flex
    justify-content: space-between
    align-items: center

    &:hover .post__image
      transform: scale(1.2)

    &__image-container
      overflow: hidden

    &__image
      width: 525px
      height: 355px
      object-fit: cover

      transition: 300ms

    &__title
      margin-bottom: 15px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 39px
      font-style: italic
    
    &__text
      width: 415px
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 16px
      letter-spacing: 0.5px
      line-height: 2
      color: #aaaaaa

    &__button
      width: 140px
      height: 50px
      margin-top: 40px

      fonta-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 16px
      font-weight: bold
      border: 1px solid #aaaaaa
      background-color: white

      cursor: pointer
      transition: 300ms

      &:hover
        color: white
        border-color: black
        background-color: #aaaaaa

    &--reverse
      flex-direction: row-reverse

@media screen and (max-width: 1600px)
  .post
    &__image
      width: 450px
      height: 300px

    &__title
      margin-bottom: 5px
      font-size: 28px

    &__text
      width: 380px
      font-size: 15px
    
    &__button
      width: 100px
      height: 40px
      margin-top: 20px
      font-size: 15px

@media screen and (max-width: 1200px)
  .post
    &__image
      width: 300px
      height: 200px

    &__title
      font-size: 22px

    &__text
      width: 280px
    
    &__button
      width: 90px
      height: 35px
      margin-top: 10px
      font-size: 13px

@media screen and (max-width: 850px)
  .post
    flex-direction: column

    &__image-container
      margin-bottom: 10px

    &__image
      width: 500px
      height: 250px

    &__text
      width: 500px

@media screen and (max-width: 520px)
  .post
    &__image
      width: 280px
      height: 150px

    &__title
      font-size: 18px

    &__text
      width: 280px
</style>