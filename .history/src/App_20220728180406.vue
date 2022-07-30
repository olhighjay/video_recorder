<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
    <div id="main-flex">
      <div class="my-sidebar">
        we are here
      </div>
      <div class="my-main">
        here we are
      </div>
    </div>
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
 
#main-flex {
  display: flex;
}
.my-sidebar {
  flex: 0 0 306px;
}




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
