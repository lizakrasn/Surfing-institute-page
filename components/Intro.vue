<template lang="pug">
  .intro
    .intro__reviews
      p.intro__title Recent Reviews
      reviewItem(
        text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed incididunt ut labore et dolore magn."
        name="- Steve Woz"
      ).intro__reviewItem
      reviewItem(
        text="Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed incididunt ut labore et dolore magn."
        name="- David Collumn"
      ).intro__reviewItem

    UserVideo(v-bind:imageUrl="require('~/assets/images/video1.png')")
    .intro__videos
      p.intro__paragraph User Videos
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
    flex-direction: row
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
</style>