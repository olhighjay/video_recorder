<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <nav class="mx-4">
      <div class="nav-logo-area">Adilo</div>
      <div class="nav-tab">Olajide</div>
      <div class="nav-profile">Adilo</div>
    </nav>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  }
}
</script>

<style>
  nav {
    display: flex;
    height: 89px;
  }
  .nav-logo-area {
    flex: 0 0 150px;
  }
  .nav-tab {
    flex: 0 0 80%px;
  }
  .nav-profile {
    flex: 0 0 150px;
  }





#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   /* text-align: center; */
   font-size: 18px;
  color: #707070;
  border: solid 1px #707070;
  width: 100vw;
  /* margin-top: 60px;  */
}
</style>
