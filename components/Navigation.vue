<template lang="pug">
  nav.navigation
    input(
      v-model="isOpenedBurgerMenu"
      type="checkbox"
      id="navigation-toggler"
    ).navigation__toggler

    label(for="navigation-toggler").navigation__toggler-label

    .div.navigation__image
      img(src="~assets/images/logo.png" alt="logo").navigation__logo

    ul.navigation__list
      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/"
          "@click.native"="closeBurgerMenu()"
        ).navigation__item-link Home

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/about"
          "@click.native"="closeBurgerMenu()"
        ).navigation__item-link About

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/blog"
          "@click.native"="closeBurgerMenu()"
        ).navigation__item-link Blog

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/contact"
          "@click.native"="closeBurgerMenu()"
        ).navigation__item-link Contact
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      isOpenedBurgerMenu: false
    }
  },
  methods: {
    closeBurgerMenu() {
      this.isOpenedBurgerMenu = false
    },
  }
})
</script>

<style lang="sass" scoped>
  .navigation
    padding: 95px 180px 0
    display: flex
    flex-direction: row
    justify-content: space-between
    align-items: flex-end
    background-color: white

    &__toggler-label
      display: none
      color: #000
      z-index: 2

    &__toggler-label::before
      content: "\2630"
      font-size: 24px
      color: black

    &__toggler:checked ~ &__toggler-label::before 
      content: "x"
      font-size: 24px
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      color: black

    &__toggler
      display: none

    &__logo
      width: 41px
      height: 33px

    &__list
      display: flex
      flex-direction: row

      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 17px
      letter-spacing: 1px
      text-transform: uppercase
      list-style-type: none

    &__item
      margin-left: 67px

    &__item-link
      color: #aaaaaa
      text-decoration: none

    &__active
      color: black

@media screen and (max-width: 1400px)
  .navigation
    padding: 95px 80px 0

@media screen and (max-width: 1200px)
  .navigation
    padding: 50px 80px 0

@media screen and (max-width: 850px)
  .navigation
    padding: 50px 50px 0

    &__list
      font-size: 15px

    &__item
      margin-left: 35px

@media screen and (max-width: 520px)
  .navigation
    padding: 30px 20px 0

    &__logo
        width: 25px
        height: 20px

    &__toggler-label
      display: inline-block

    &__list
      position: absolute
      top: 0
      left: 0
      width: 100%
      height: 100vh
      flex-direction: column
      align-items: center
      padding: 150px 0

      background-color: white
      z-index: 1

    &__item
      margin: 0
      padding-bottom: 30px
      font-size: 30px

    &__toggler:not(:checked) ~ &__list
      transform: translate(-100%, 0)
</style>