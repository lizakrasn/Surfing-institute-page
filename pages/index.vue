<template>
  <div>
    <Header />
    <Intro />
    <Instractors />
    <BlogOfPosts />
    <Enroll />
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Intro from '@/components/Intro'
import Instractors from '@/components/Instractors'
import BlogOfPosts from '@/components/BlogOfPosts'
import Enroll from '@/components/Enroll'
import Footer from '@/components/Footer'
export default {
  components: {
    Header,
    Intro,
    Instractors,
    BlogOfPosts,
    Enroll,
    Footer
  }
}
</script>

<style lang="sass">
  .animation-fadeIn
    animation: fadeIn ease 3s

  @keyframes fadeIn
    0%
      opacity:0
      transform: scale(0.5)
    100%
      opacity:1
      transform: scale(1)
</style>
