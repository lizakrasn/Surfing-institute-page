<template lang="pug">
  .footer
    .footer__container
      .footer__company-info
        p.footer__company Beach Surfing
        p.footer__comment Copyright © 2018 All Rights Reserved.
      p.footer__designer Designed by 
        span.footer__span Rikon Rahman
</template>

<style lang="sass" scoped>
  .footer
    border-top: 1px solid #F0EBE4

    &__container
      height: 140px
      max-width: 1300px
      margin: 0 auto
      padding: 0 50px 40px
      position: reletive

      display: flex
      justify-content: space-between
      align-items: flex-end

    &__company
      margin-bottom: 10px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 24px
      letter-spacing: 0.5px
      font-weight: bold

    &__comment
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 15px
      letter-spacing: 0.5px
      color: #aaaaaa
    
    &__designer
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 15px
      letter-spacing: 0.5px
      color: #aaaaaa

    &__span
      color: black

@media screen and (max-width: 1600px)
  .footer
    &__container
      height: 120px
      padding: 0 80px 30px

    &__company
      margin-bottom: 5px
      font-size: 20px

@media screen and (max-width: 850px)
  .footer
    &__container
      height: 80px
      padding: 0 50px 20px

    &__company
      margin-bottom: 5px
      font-size: 15px

    &__comment,
    &__designer
      font-size: 12px

@media screen and (max-width: 520px)
  .footer
    &__container
      padding: 0 20px 10px
      flex-direction: column
      justify-content: flex-end
      align-items: center

    &__company
      font-size: 12px
      text-align: center
</style>