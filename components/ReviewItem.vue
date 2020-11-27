<template lang="pug">
  .reviewItem
    p.reviewItem__text {{text}}
    p.reviewItem__name {{name}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "reviewItem",
  props: ['text', 'name']
})
</script>

<style lang="sass" scoped>
  .reviewItem
    width: 265px
    position: relative

    &::after
      width: 260px
      display: block

      content: ""
      border-top: 1px solid #aaaaaa
    
    &::before
      width: 50px
      height: 50px
      position: absolute
      left: -18px
      top: 5px
      z-index: -1

      content: ""
      background-image: url("~assets/images/quotes.png")
      background-repeat: no-repeat

    &__text
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-style: italic
      line-height: 2
      letter-spacing: 0.5px

      color: #aaaaaa

    &__name
      margin: 10px 0 20px
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-weight: bold
      letter-spacing: 0px
</style>