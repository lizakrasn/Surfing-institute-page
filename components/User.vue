<template lang="pug">
  .user
    img(v-bind:src="imageUrl").user__photo
    .user__info
      a(href="#" @click.prevent="openUser(user.id)").user__name {{user.name}}
      p.user__email Email: {{user.email}}
      p.user__phone Phone: {{user.phone}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "User",
  props: {
    user: {
      type: Object,
      required: true
    },
    index: Number,
    imageUrl: String
  },
  methods: {
    openUser(userId) {
      this.$router.push('/about/' + userId)
    }
  }
})
</script>

<style lang="sass" scoped>
  .user
    padding: 10px 0
    padding-left: calc(50% - 200px)
    display: flex
    justify-content: flex-start
    align-items: center

    font-family: 'Playfair Display', 'Times New Roman', Times, serif
    font-size: 15px
    transition: 300ms

    &:hover
      background-color: #D7EFF6

    &__photo
      width: 200px
      height: 200px
      object-fit: cover

      border: 5px solid #aaaaaa
      border-radius: 50%
    
    &__info
      margin-left: 40px

    &__name
      font-size: 24px
      font-weight: bold
      color: black
      text-decoration: none
      transition: 300ms

      &:hover
        color: blue

@media screen and (max-width: 500px)
  .user
    width: 100%
    padding: 10px

    &__photo
      width: 80px
      height: 80px

    &__info
      margin-left: 10px

    &__name
      font-size: 20px
      font-weight: bold
</style>