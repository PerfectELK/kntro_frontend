<template>
  <div class="app__container">
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
    .app__container{
      height: 100vh;
      display: flex;
      flex-direction: column;
    }
</style>
