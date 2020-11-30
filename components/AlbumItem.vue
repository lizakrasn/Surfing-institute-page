<template lang="pug">
  .album
    .album__container
      img(v-bind:src="imageUrl").album__image
      p.album__name-title Album name:
      p.album__name {{album.title}}
</template>

<script lang="ts">
import Vue from 'vue'
import Loader from '@/components/Loader'
export default Vue.extend({
  data() {
    return {
      imageUrl: null,
    }
  },
  name: "AlbumItem",
  props: ["album"],
  mounted() {
    fetch('http://jsonplaceholder.typicode.com/photos?albumId=' + this.album.id)
      .then(response => response.json())
      .then(json => {
        this.imageUrl = json[0].url
      })
  },
  components: {
    Loader
  }
})
</script>

<style lang="sass" scoped>
  .album
    width: 280px
    padding: 10px
    border: 3px solid transparent
    border-radius: 10px
    transition: 300ms

    &:hover
      background-color: #aaaaaa
      border-color: #aaaaaa
    &__container
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 15px

    &__image
      width: 100%
      height: 400px

      object-fit: cover
    
    &__name-title
      margin-top: 10px
      font-weight: bold

@media screen and (max-width: 1000px)
  .album
    width: 200px

    &__image
      height: 250px
</style>