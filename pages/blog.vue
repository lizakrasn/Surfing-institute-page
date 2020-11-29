<template lang="pug">
  .blog
    h1.blog__title Posts
    ul.blog__posts-list
      PostOfBlog(
        v-for="(post, i) of posts"
        v-bind:post="post"
        v-bind:index="i"
        v-bind:key="post.id"
        v-bind:imageUrl="require(`~/assets/images/imagesOfPosts/${images[post.id % images.length]}`)"
      ).blog__post
</template>

<script lang="ts">
import Vue from 'vue'
import PostOfBlog from "@/components/PostOfBlog"
export default Vue.extend({
  data() {
    return {
      posts: [],
      images: [
        "billy-1.jpg",
        "cape-town.jpg",
        "cliff.jpg",
        "deserts.jpg",
        "greg-long.jpg",
        "jordy.jpg",
        "kani-heff.jpg",
        "mulcoy.jpg",
        "mulcoy-alask.jpg",
        "twiggy.jpg",
        "ryan-burch.jpg",
      ]
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => response.json())
      .then(json => {
        this.posts = json
      })
  },
  components: {
    PostOfBlog
  },
})
</script>

<style lang="sass" scoped>
  .blog
    padding: 50px

    &__posts-list
      padding: 0

    &__title
      margin-bottom: 50px

      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 38px
      text-align: center

    &__post
      margin-bottom: 20px

@media screen and (max-width: 750px)
  .blog
    padding: 30px
    &__title
      margin-bottom: 20px

@media screen and (max-width: 500px)
  .blog
    padding: 20px

    &__title
      margin-bottom: 10px
      font-size: 26px
</style>