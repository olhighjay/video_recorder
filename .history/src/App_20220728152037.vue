<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <nav class="">
      <div class="nav-logo-area">
        <div class="nav-logo-area-inner">
          <div style="padding-top:21px">
            <span style="background-color:#FBBD71; padding:5px; border-radius:10px">
            <img alt="Adilo logo" src="./assets/swarm.png">
            </span>
          </div>
          <div style="font-size:28px; margin-left:15px; font-weight:bold; color:#21455E; padding-top:14px">Adilo</div>
        </div>
      </div>
      <div class="nav-tab">
        <ul class="my-nav-list">
          <li>Projects</li>
          <li>Tools & App</li>
          <li>Channels</li>
          <li>Contacts</li>
          <li>Analytics</li>
          <li>Settings</li>
        </ul>
      </div>
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
    /* height: 69px; */
    padding: 0 0.032%;
  }
  .nav-logo-area, .nav-profile {
    flex: 0 0 19%;
  }
  .nav-logo-area {
    padding-left: 3.2%;
    padding-top: 21px;
    padding-bottom: 27px;
  }
  .nav-logo-area-inner {
    display: flex;
  }
  .nav-tab {
    flex: 0 0 62%;
  }
  /* .nav-profile {
    flex: 0 0 10%;
  } */
  .my-nav-list {
    list-style: none;
  }
  .my-nav-list>li {
    display: inline;
    margin-right: 20px;
    margin-top: 50px;
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
