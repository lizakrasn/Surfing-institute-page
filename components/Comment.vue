<template lang="pug">
  .comment
    p.comment__name {{comment.name}}
    p.comment__text {{comment.body}}
    p.comment__email Email: {{comment.email}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "Comment",
  props: {
    comment: {
      type: Object,
      required: true
    },
    index: Number,
  },
})
</script>

<style lang="sass" scoped>
  .comment
    width: 300px
    padding: 20px
    font-family: 'Myriad Pro Regular', Helvetica, sans-serif

    background-color: white
    border: 2px solid #aaaaaa
    border-radius: 20px

    &:hover
      background-color: #aaaaaa
      border-color: black

    &__text
      margin: 10px 0
      font-size: 17px

    &__name
      font-size: 22px
      text-transform: capitalize

    &__email
      font-size: 15px

@media screen and (max-width: 700px)
  .comment
    width: 220px
    padding: 20px

    &__text
      font-size: 15px

    &__name
      font-size: 17px
</style>