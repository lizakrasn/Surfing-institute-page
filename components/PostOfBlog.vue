<template lang="pug">
  li.post
    img(v-bind:src="imageUrl").post__image
    .post__info
      a(v-bind:href="'/blog/' + post.id" target="_blank").post__title {{post.title}}
      p.post__text {{post.body}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "PostOfBlog",
  props: {
    post: {
      type: Object,
      required: true
    },
    index: Number,
    imageUrl: String
  }
})
</script>

<style lang="sass" scoped>
  .post
    padding: 30px
    display: flex
    align-items: center

    background-color: rgb(186, 225, 225, 0.5)
    border-radius: 10px
    transition: 300ms

    &:hover
      background-color: rgb(186, 225, 225, 1)

    &:hover .post__image
        transform: scale(1.1)

    &__image
      width: 300px
      height: 200px
      object-fit: cover

      border-radius: 20px
      transition: 300ms

    &__info
      padding-left: 40px
    
    &__title
      margin-bottom: 15px

      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 24px
      text-transform: capitalize
      text-decoration: none
      color: black
      cursor: pointer

      &:hover
        color: blue

    &__text
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 15px

@media screen and (max-width: 750px)
  .post
    flex-direction: column

    &__image
      width: 350px
      height: 200px

    &__info
      padding: 20px 0 0
    
    &__title
      margin-bottom: 10px
      font-size: 20px

@media screen and (max-width: 500px)
  .post
    &__image
      width: 220px
      height: 150px

    &__info
      padding: 20px 0 0
    
    &__title
      margin-bottom: 10px
      font-size: 20px
</style>