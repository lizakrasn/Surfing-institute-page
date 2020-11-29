<template lang="pug">
  .enroll
    p.enroll__title Aren't you intrested Yet!
    button.enroll__button Enroll Now
</template>

<style lang="sass" scoped>
  .enroll
    padding-bottom: 145px
    display: flex
    flex-direction: column
    align-items: center

    &__title
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 50px
      letter-spacing: 1px
      text-align: center

    &__button
      width: 180px
      height: 55px
      padding: 0
      margin-top: 78px

      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 18px
      letter-spacing: 1px

      border: 1px solid black
      background-color: white

      cursor: pointer
      transition: 300ms

      &:hover
        background-color: #aaaaaa
        color: white

@media screen and (max-width: 1400px)
  .enroll
    padding-bottom: 120px

    &__title
      font-size: 40px

    &__button
      width: 130px
      height: 45px
      margin-top: 50px
      font-size: 15px

@media screen and (max-width: 520px)
  .enroll
    padding-bottom: 80px

    &__title
      font-size: 20px

    &__button
      width: 100px
      height: 35px
      margin-top: 25px
      font-size: 15px
</style>