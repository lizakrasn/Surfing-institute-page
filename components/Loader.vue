<template lang="pug">
  .loader
      p.loader__text Loading...
      progress.loader__progress
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: "Loader"
})
</script>

<style lang="sass" scoped>
  .loader
    width: 100%
    &__text
      color: #aaaaaa
      fornt-font-family: 'Myriad Pro Regular', Helvetica, sans-serif
      font-size: 24px
    
    &__progress
      width: 100%
</style>