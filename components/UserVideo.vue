<template lang="pug">
  .video
    img(v-bind:src="imageUrl" alt="surfing").video__item
    button(type="button").video__play &#9654;
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "UserVideo",
  props: ["imageUrl"]
})
</script>

<style lang="sass" scoped>
  .video
    width: 617px
    height: 436px
    position: relative
    overflow: hidden

    &:hover .video__item
      transform: scale(1.2)

    &__item
      width: 100%
      height: 100%
      object-fit: cover

      transition: 300ms

    &__play
      position: absolute
      padding: 0
      bottom: 30px
      left: 25px
      width: 55px
      height: 55px

      background-color: white
      border: none
      border-radius: 50px

      transition: 300ms
      cursor: pointer

      &:hover
        background-color: #aaaaaa

    &--small
      width: 280px
      height: 157px

      .video__play
        bottom: -15px
        left: -10px

@media screen and (max-width: 1600px)
  .video
    width: 530px
    height: 380px

    &--small
      width: 200px
      height: 120px

@media screen and (max-width: 1200px)
  .video
    width: 500px
    height: 360px

    &--small
      width: 230px
      height: 150px

@media screen and (max-width: 540px)
  .video
    width: 280px
    height: 160px

    &__play
      bottom: 10px
      left: 10px
      width: 35px
      height: 35px

    &--small
      width: 130px
      height: 100px

      .video__play
        bottom: -5px
        left: -5px
</style>