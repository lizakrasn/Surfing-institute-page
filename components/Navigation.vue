<template lang="pug">
  nav.navigation
    .div.navigation__image
      img(src="~assets/images/logo.png" alt="logo").navigation__logo
    
    ul.navigation__list
      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/"
        ).navigation__item-link Home

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/about"
        ).navigation__item-link About

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/blog"
        ).navigation__item-link Blog

      li.navigation__item
        nuxt-link(
          exact
          active-class="navigation__active"
          to="/contact"
        ).navigation__item-link Contact
</template>

<style lang="sass" scoped>
  .navigation
    padding: 95px 180px 0
    display: flex
    flex-direction: row
    justify-content: space-between
    align-items: flex-end

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
    
    &__list
      display: none
</style>