<template lang="pug">
  .instractors
    h1.instractors__title Popular Instractors
    .instractors__gallery-container
      .instractors__button.instractors__button-left
      .instractors__gallery
        Instractor(
          v-bind:imageUrl="require('~/assets/images/instractor1.png')"
          name="Simon Adward"
          comment="5,000 students"
        ).instractors__gallery-item
        Instractor(
          v-bind:imageUrl="require('~/assets/images/instractor2.png')"
          name="Elliana D`Soza"
          comment="4,350 students"
        ).instractors__gallery-item
        Instractor(
          v-bind:imageUrl="require('~/assets/images/instractor3.png')"
          name="Joseph Bardon"
          comment="3,248 students"
        ).instractors__gallery-item
      .instractors__button.instractors__button-right
    .instractors__dots
      .instractors__dots-item
      .instractors__dots-item.instractors__dots-item--active
      .instractors__dots-item
</template>

<script lang="ts">
import Vue from 'vue'
import Instractor from '@/components/Instractor'
export default Vue.extend({
  components: {
    Instractor
  }
})
</script>

<style lang="sass" scoped>
  .instractors
    margin: 0 auto
    padding: 220px 0 180px

    &__title
      margin-bottom: 87px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 50px
      font-weight: normal
      letter-spacing: 0.5px
      text-align: center

    &__gallery-container
      display: flex
      flex-direction: row
      justify-content: center
      align-items: center

    &__gallery
      width: 1056px
      margin: 0 70px
      display: flex
      flex-direction: row
      justify-content: space-between

    &__button
      width: 40px
      height: 70px
      background-repeat: no-repeat
      background-size: contain
      cursor: pointer

    &__button-left
      background-image: url("~assets/images/arrowLeft.png")

    &__button-right
      background-image: url("~assets/images/arrowRight.png")

    &__dots
      width: 70px
      margin: 50px auto 0
      display: flex
      justify-content: space-between

    &__dots-item
      width: 13px
      height: 13px

      border: 2px solid black
      border-radius: 50px

    &__dots-item--active
      background-color: black

@media screen and (max-width: 1600px)
  .instractors
    &__title
      margin-bottom: 50px
      font-size: 38px

    &__gallery
      width: 900px
      margin: 0 30px

    &__button
      width: 30px
      height: 55px

@media screen and (max-width: 1400px)
  .instractors
    padding: 180px 0

@media screen and (max-width: 1200px)
  .instractors
    &__title
      margin-bottom: 25px
      font-size: 28px

    &__gallery
      width: 700px
      margin: 0 30px

    &__button
      width: 20px
      height: 35px

@media screen and (max-width: 850px)
  .instractors
    padding: 180px 0

    &__gallery
      width: 420px
      margin: 0 15px
      overflow: hidden
    
    &__gallery-item
      margin-right: 20px

    &__button
      width: 15px
      height: 25px

    &__dots
      width: 50px
      margin: 25px auto 0

    &__dots-item
      width: 10px
      height: 10px
      border: 1px solid black

@media screen and (max-width: 520px)
  .instractors
    padding: 60px 0 80px

    &__gallery
      width: 200px

    &__title
      margin-bottom: 15px
      font-size: 20px

    &__dots
      margin: 10px auto 0
</style>