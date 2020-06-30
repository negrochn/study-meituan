<template>
  <div>
    <Header />
    <nuxt />
    <BottonNav />
  </div>
</template>

<script>
import Header from '@/components/header'
import BottonNav from '@/components/botton-nav'

export default {
  name: 'LayoutsDefault',
  components: {
    Header,
    BottonNav
  }
}
</script>

<style>
</style>
