<template lang="pug">
  .intro
    .intro__reviews-container
      p.intro__title Recent Reviews
      .intro__reviews
        reviewItem(
          text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed incididunt ut labore et dolore magn."
          name="- Steve Woz"
        ).intro__reviewItem
        reviewItem(
          text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed incididunt ut labore et dolore magn."
          name="- David Collumn"
        ).intro__reviewItem

    UserVideo(v-bind:imageUrl="require('~/assets/images/video1.png')")
    .intro__videos-container
      p.intro__paragraph User Videos
      .intro__videos
        UserVideo(v-bind:imageUrl="require('~/assets/images/video2.png')").video--small
        UserVideo(v-bind:imageUrl="require('~/assets/images/video3.png')").video--small
</template>

<script lang="ts">
import Vue from 'vue'
import ReviewItem from '@/components/ReviewItem'
import UserVideo from '@/components/UserVideo'
export default Vue.extend({
  components: {
    ReviewItem,
    UserVideo
  }
})
</script>

<style lang="sass" scoped>
  .intro
    padding: 0 180px
    display: flex
    justify-content: space-between
    align-items: flex-end

    &__title
      margin-bottom: 40px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 36px
    
    &__paragraph
      margin-bottom: 22px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 36px

    &__reviews
      width: 280px

      .intro__reviewItem:first-of-type
        margin-bottom: 42px

    &__videos
      .video--small:first-of-type
        margin-bottom: 35px

@media screen and (max-width: 1600px)
  .intro
    &__title
      margin-bottom: 20px
      font-size: 28px
    
    &__paragraph
      margin-bottom: 15px
      font-size: 28px
    
    &__reviews
      width: 260px

      .intro__reviewItem:first-of-type
        margin-bottom: 30px

@media screen and (max-width: 1400px)
  .intro
    padding: 0 80px

@media screen and (max-width: 1200px)
  .intro
    flex-direction: column
    justify-content: center
    align-items: center

    &__title
      margin-bottom: 20px
      text-align: center
    
    &__reviews-container
      margin-bottom: 20px

    &__reviews
      width: 470px

      .intro__reviewItem:first-of-type
        margin-bottom: 10px

    &__paragraph
      margin: 10px 0
      font-size: 24px
      text-align: center

    &__videos
      width: 500px
      display: flex
      justify-content: space-between
</style>