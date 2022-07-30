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
          <li><a>Projects</a></li>
          <li style="border-top: 6px solid #0DABD8"> <a>Tools & App</a></li>
          <li><a>Channels</a></li>
          <li><a>Contacts</a></li>
          <li><a>Analytics</a></li>
          <li><a>Settings</a></li>
        </ul>
      </div>
      <div class="nav-profile">
        <ul class="my-nav-list">
          <li><a>Help</a></li>
        </ul>
        <div style="padding-top:35px; ">
          <div style="border-left: 1px solid #A3BAC6; padding-left:25px">
            <img alt="Adilo logo" src="./assets/profile.jpg" style="width:35px; height: 35px; border-radius:10px">
            <span>Ifeoluwa Olajide </span>
            <span style="display:inline">ifeoluwaolajide@gmail.com</span>
          </div>
        </div>
      </div>
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

  .nav-logo-area {
    flex: 0 0 19%;
    padding-left: 3.2%;
    padding-top: 19px;
    padding-bottom: 27px;
  }
  .nav-logo-area-inner {
    display: flex;
  }
  .nav-tab {
    flex: 0 0 51%;
  }
  .nav-profile {
    flex: 0 0 30%;
    display: flex;
  }
  .my-nav-list {
    list-style: none;
    padding-top: 40px;
  }
  .my-nav-list>li {
    display: inline;
    margin-right: 25px;
    padding-top: 40px;
  }
  .my-nav-list>li>a {
    text-align: left;
    font: normal normal normal 18px/27px Poppins;
    letter-spacing: 0px;
    color: #707070;
    opacity: 1
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
