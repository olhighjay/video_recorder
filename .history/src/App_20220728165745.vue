<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Navbar from './layouts/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

<style>
 



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   /* text-align: center; */
   font-size: 18px;
  color: #707070;
  border: solid 2px #E2E5ED;
  width: 100vw;
  /* margin-top: 60px;  */
}
</style>
