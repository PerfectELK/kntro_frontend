<template>
  <div>
    <Navbar/>
    <nuxt />
    <Footer/>
  </div>
</template>


<script>
  import Navbar from '~/layouts/_/Navbar.vue'
  import Footer from '~/layouts/_/Footer.vue'

  export default {
      components:{
          Navbar, Footer
      }
  }
</script>


<style lang="scss">

</style>
