<template lang="pug">
  .about
    p.about__title Users
    Loader(v-if="users===null").about__loader
    ul(v-else).about__users
      User(
        v-for="(user, i) of users",
        v-bind:user="user",
        v-bind:index="i"
        v-bind:key="user.id"
        v-bind:imageUrl="require(`~/assets/images/users/${images[user.id % images.length]}`)"
      ).about__user-item
</template>

<script lang="ts">
import Vue from 'vue'
import Loader from "@/components/Loader"
import User from "@/components/User"
export default Vue.extend({
  data() {
    return {
      users: null,
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
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())
      .then(json => {
        this.users = json
      })
  },
  components: {
    Loader,
    User
  }
})
</script>

<style lang="sass" scoped>
  .about
    &__loader
      padding: 0 50px

    &__users
      padding: 0

    &__title
      margin: 30px 0
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 38px
      text-align: center

    &__user-item
      margin-bottom: 20px

@media screen and (max-width: 500px)
  .about
    &__title
      margin: 10px 0
      font-size: 26px

    &__user-item
      margin-bottom: 10px
</style>