<template lang="pug">
  Loader(v-if="user===null").loader
  .user(v-else)
    .user__info-container
      img(v-bind:src="require(`~/assets/images/users/${images[this.$route.params.id % images.length]}`)").user__photo
      .user__info
        p.user__name {{user.name}}
        p.user__email Email: {{user.email}}
        p.user__phone Phone: {{user.phone}}
    p.user__title Albums
    Loader(v-if="albums===null").user__loader.loader
    ul(v-else).user__albums
      AlbumItem(
        v-for="(album, i) of albums",
        v-bind:album="album",
        v-bind:index="i"
        v-bind:albumId="album.id"
        v-bind:key="album.id"
       )
      
</template>

<script lang="ts">
import Vue from 'vue'
import AlbumItem from '@/components/AlbumItem'
import Loader from "@/components/Loader"
export default Vue.extend({
  data() {
    return {
      user: null,
      albums: null,
      images: [
        "user1.jpg",
        "user2.png",
        "user3.png",
        "user4.jpeg",
        "user5.png",
        "user6.jpg",
        "user7.jpg",
        "user8.jpg",
        "user9.jpeg",
        "user10.jpg",
      ]
    }
  },
  mounted() {
    fetch('http://jsonplaceholder.typicode.com/users/' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.user = json
      }),

    fetch('http://jsonplaceholder.typicode.com/albums?userId=' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.albums = json
      })
  },
  components: {
    Loader,
    AlbumItem
  }
})
</script>

<style lang="sass" scoped>
  .loader
    padding: 0 50px

  .user
    font-family: 'Playfair Display', 'Times New Roman', Times, serif
    font-size: 17px

    &__info-container
      padding: 40px
      display: flex
      justify-content: flex-start
      align-items: center

      &:hover .user__photo
        transform: scale(1.1)

    &__photo
      width: 400px
      height: 400px
      object-fit: cover

      border: 5px solid #aaaaaa
      border-radius: 50%
      transition: 300ms
    
    &__info
      margin-left: 80px

    &__name
      font-size: 34px
      font-weight: bold
      text-decoration: none

    &__title
      font-size: 30px
      text-transform: uppercase
      text-align: center

    &__albums
      margin: 30px 150px
      padding: 0
      display: flex
      overflow: hidden
</style>