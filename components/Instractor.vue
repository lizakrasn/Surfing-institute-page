<template lang="pug">
  .instractor
    img.instractor__photo(v-bind:src="imageUrl" alt="surfer")
    p.instractor__name {{name}}
    p.instractor__comment {{comment}}
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "Instractor",
  props: ["imageUrl", "name", "comment"]
})
</script>


<style lang="sass" scoped>
  .instractor
    transition: 500ms

    &:hover .instractor__photo
      filter: contrast(1)

    &__photo
      width: 290px
      height: 353px
      object-fit: cover
      filter: contrast(0.6)
      transition: 500ms

    &__name
      margin: 25px 0 10px
      font-family: 'Playfair Display', 'Times New Roman', Times, serif
      font-size: 30px
      letter-spacing: 0.5px
      text-align: center

    &__comment
      font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 15px
      font-weight: bold
      text-align: center
      letter-spacing: 1px
      color: #2ab738

@media screen and (max-width: 1600px)
  .instractor
    &__photo
        width: 230px
        height: 310px

    &__name
      margin: 15px 0 5px
      font-size: 25px

@media screen and (max-width: 1200px)
  .instractor
    &__photo
      width: 200px
      height: 290px

@media screen and (max-width: 520px)
  .instractor
    &__name
      margin: 5px
      font-size: 18px
</style>