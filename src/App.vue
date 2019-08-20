<template>
  <div id="app">
    <NavBar/>
    <router-view/>
    <Bottom/>
  </div>
</template>

<script>
import NavBar from './views/_/NavBar.vue'
import Bottom from './views/_/Bottom.vue'
export default {
  name: 'App',
  components: {
    NavBar, Bottom
  }
}
</script>
