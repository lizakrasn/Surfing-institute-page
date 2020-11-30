<template lang="pug">
  .contact
    .contact__background
    .contact__info
      p.contact__title Contact us
      a(href="tel:+380-00-00-00-000").contact__text +380-00-00-00-000
      a(href = "mailto: surfingInstitute@gmail.com").contact__text surfingInstitute@gmail.com

</template>

<style lang="sass" scoped>
  .contact
    font-family: 'Myriad Pro Regular', Helvetica, sans-serif
    font-size: 17px
    line-height: 2

    &__background
      width: 100%
      height: 100vh
      position: absolute
      top: 0
      left: 0
      z-index: -1

      background-image: url('~assets/images/imagesOfPosts/cliff.jpg')
      background-repeat: no-repeat
      background-size: cover
      opacity: 0.7

      animation: fadeIn 3s

    &__info
      width: fit-content
      margin: 200px auto 0
      padding: 20px
      border-radius: 20px
      background-color: rgb(255, 255, 255,0.5)
      transition: 300ms

      &:hover
        transform: scale(1.1)

    &__title
      font-size: 26px
      text-transform: uppercase
      text-align: center

    &__text
      display: block
      text-align: center
      text-decoration: none
      color: black

      cursore: pointer

  @keyframes fadeIn
    0%
      opacity: 0

    100%
      opacity: 0.7


</style>