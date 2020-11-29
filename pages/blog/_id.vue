<template lang="pug">
  .post
    .post__info-container
      img(v-bind:src="require(`~/assets/images/imagesOfPosts/${images[this.$route.params.id % images.length]}`)").post__image
      .post__info
        p.post__title {{post ? post.title : "Loading..."}}
        p.post__text {{post ? post.body : "Loading..."}}
    p.post__comments-title Comments:
    .post__comments
      Comment(
        v-for="(comment, i) of comments"
        v-bind:comment="comment"
        v-bind:index="i"
        v-bind:key="comment.id"
      ).post__comment-item
</template>

<script lang="ts">
import Vue from 'vue'
import Comment from '@/components/Comment'
export default Vue.extend({
  data() {
    return {
      post: null,
      comments: null,
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
    fetch('https://jsonplaceholder.typicode.com/posts/' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.post = json
      })

    fetch('http://jsonplaceholder.typicode.com/comments?postId=' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.comments = json
      })
  }
})
</script>

<style lang="sass" scoped>
  .post
    margin: 30px
    padding: 50px
    background-color: #D7EFF6
    border-radius: 10px

    &__info-container
      display: flex
      align-items: center

    &__image
      width: 500px
      height: 300px
      object-fit: cover

      border-radius: 20px
      transition: 300ms

      &:hover
          transform: scale(1.1)

    &__info
      padding-left: 40px
    
    &__title
      margin-bottom: 25px

      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 38px
      text-transform: capitalize
      text-decoration: none

    &__text
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 17px

    &__comments-title
      margin: 30px 0
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 30px
      text-align: center
    
    &__comments
      margin: auto
      display: flex
      flex-wrap: wrap
      width: 1020px

    &__comment-item
      margin: 20px

@media screen and (max-width: 1200px)
  .post
    &__info-container
      flex-direction: column
    
    &__image
      width: 600px
      height: 400px

    &__info
      padding-left: 0px
      margin-top: 30px
    
    &__comments
      width: 220px

    &__comment-item
      margin: 0
      margin-bottom: 10px

@media screen and (max-width: 700px)
  .post
    margin: 20px
    padding: 20px

    &__image
      width: 220px
      height: 200px

    &__title
      margin-bottom: 10px
      font-size: 20px

    &__text
      font-size: 15px
</style>