<template lang="pug">
  .header
    h1.header__title Long Beach Surfing Institute
    p.header__subtitle Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.
</template>

<style lang="sass" scoped>
  .header
    padding: 200px 0 205px

    &__title
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-weight: normal
      font-size: 68px
      letter-spacing: 1px
      text-align: center
    
    &__subtitle
      margin: 20px auto 0
      width: 620px

      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 15px
      line-height: 2
      letter-spacing: 1px
      text-align: center
      color: #aaaaaa

@media screen and (max-width: 1400px)
  .header
    padding: 180px 0

    &__title
      font-size: 52px
</style>