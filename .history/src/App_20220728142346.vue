<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <nav class="mx-4">
      <div class="nav-logo-area">
        <span style="background-color:#FBBD71; padding:8px; border-radius:5px"><img alt="Vue logo" src="./assets/swarm.png"></span>
        Adilo
      </div>
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
    height: 69px;
    padding: 0 0.032%;
  }
  .nav-logo-area, .nav-profile {
    flex: 0 0 19%;
  }
  .nav-tab {
    flex: 0 0 62%;
  }
  /* .nav-profile {
    flex: 0 0 10%;
  } */





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
