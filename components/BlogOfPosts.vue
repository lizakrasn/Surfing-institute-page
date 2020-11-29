<template lang="pug">
  .blog
    p.blog__title Recent Blogs By User
    .blog__posts-container
      Post(
        v-bind:imageUrl="require('~/assets/images/post1.png')"
        title="Lipsum cound be headline"
        text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam."
      ).blog__post
      Post(
        v-bind:imageUrl="require('~/assets/images/post2.png')"
        title="Lipsum cound be headline"
        text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam."
      ).blog__post.post--reverse
</template>

<script lang="ts">
import Vue from 'vue'
import Post from '@/components/Post'
export default Vue.extend({
  components: {
    Post
  }
})
</script>

<style lang="sass" scoped>
  .blog
    padding-bottom: 240px

    &__posts-container
      width: 1056px
      margin: 0 auto

      & .post:first-child
        margin-bottom: 190px

    &__title
      margin-bottom: 90px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 50px
      font-weight: normal
      letter-spacing: 0.5px
      text-align: center

@media screen and (max-width: 1600px)
  .blog
    &__posts-container
      width: 900px

    & .post:first-child
      margin-bottom: 100px
    
    &__title
      margin-bottom: 50px
      font-size: 38px

@media screen and (max-width: 1400px)
  .blog
    padding-bottom: 180px

@media screen and (max-width: 1200px)
  .blog
    &__posts-container
      width: 700px
</style>