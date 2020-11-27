<template>
  <div>
    <Navigation />

    <main>
      <div class="container">
        <Nuxt />
      </div>
    </main>
  </div>
</template>

<script>
import Navigation from '@/components/Navigation'
export default {
  components: {
    Navigation
  }
}
</script>

<style lang="sass">
  *
    box-sizing: border-box

  html,
  body,
  ul,
  li,
  h1,
  p
    margin: 0
  //font-family: 'Playfair Display', serif;
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap')

  @font-face
    font-family: 'Myriad Pro Regular'
    font-style: normal
    font-weight: normal
    src: local('Myriad Pro Regular'), url('~assets/fonts/MYRIADPRO-REGULAR.woff') format('woff')
</style>
