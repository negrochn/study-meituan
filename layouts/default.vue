<template>
  <div>
    <Header />
    <nuxt />
    <BottonNav />
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/header'
import BottonNav from '@/components/botton-nav'
import Footer from '@/components/footer'

export default {
  name: 'LayoutsDefault',
  components: {
    Header,
    BottonNav,
    Footer
  }
}
</script>

<style>
</style>
