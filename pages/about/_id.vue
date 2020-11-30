<template lang="pug">
  Loader(v-if="user===null").loader
  .user(v-else)
    .user__info-container
      img(v-bind:src="require(`~/assets/images/users/${images[this.$route.params.id % images.length]}`)").user__photo
      .user__info
        p.user__name {{user.name}}
        p.user__email Email: {{user.email}}
        p.user__phone Phone: {{user.phone}}
    p.user__title 
    Loader(v-if="albums===null").user__loader.loader
    swiper(v-else :options="swiperOption").swiper.user__albums
      swiper-slide(
        v-for="(album, i) of albums",
        v-bind:index="i",
        v-bind:key="album.id"
      )
        AlbumItem(
          v-bind:album="album",
          v-bind:albumId="album.id"
        )
      .swiper-button-prev(slot="button-prev")
      .swiper-button-next(slot="button-next")
</template>

<script lang="ts">
import Vue from 'vue'
import AlbumItem from '@/components/AlbumItem'
import Loader from "@/components/Loader"
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

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
      ],
      swiperOption: {
          slidesPerView: 3,
          spaceBetween: 25,
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          },
          breakpoints: {
            1200: {
              slidesPerView: 3,
              spaceBetween: 15
            },
            1000: {
              slidesPerView: 3,
              spaceBetween: 15
            },
            700: {
              slidesPerView: 3,
              spaceBetween: 15
            },
            500: {
              slidesPerView: 2,
              spaceBetween: 15
            },
            300: {
              slidesPerView: 1,
              spaceBetween: 15
            }
          }
        }
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/users/' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.user = json
      }),

    fetch('https://jsonplaceholder.typicode.com/albums?userId=' + this.$route.params.id)
      .then(response => response.json())
      .then(json => {
        this.albums = json
      })
  },
  components: {
    Loader,
    AlbumItem,
    Swiper,
    SwiperSlide
  },
  directives: {
    swiper: directive
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
      margin: 30px 100px
      padding-left:50px
      padding-right:50px
      display: flex
      overflow: hidden

@media screen and (max-width: 1000px)
  .user
    &__info-container
      padding: 20px

    &__photo
      width: 200px
      height: 200px
    
    &__info
      margin: 20px 0 0

    &__albums
      margin: 0 20px

@media screen and (max-width: 500px)
  .user
    &__info-container
      flex-direction: column
      justify-content: center

    &__photo
      width: 200px
      height: 200px

    &__albums
      margin: 0 10px
</style>