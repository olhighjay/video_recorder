<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
    <div id="main-flex">
      <div class="my-sidebar">
`        <ul class="my-sidebar-items">
            <li> <img src="./assets/video-player.png" alt=""> &nbsp; My Recordings</li>
            <li> <i class="fa fa-share-alt" style="color:#2c4f8f"></i> &nbsp; Requested</li>
          </ul>
`      </div>
      <div class="my-main">
        here we are hbjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjj
        54ye45yhe56ur5u7r67iur67ir67iur67u
        r67ur67iur67ir67ir67kti67i 6r67itui75767ur67i
        567it67i67 i5657it78i
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
  flex: 0 0 240px;
  height: 100vh;
  background-color: #ebf2f656;
  border-right: 2px solid #21455e54;
  /* border-right: 2px solid #21455E; */
  /* width:250px; */
}
.my-sidebar-items {
  list-style: none;
  padding: 0;
}
.my-sidebar-items>li {
  margin : 10px 12px 10px 18px;
  padding: 7px 20px ;
  background-color: red;
}





.my-main {
  flex: 1;
  flex-wrap: wrap;
}



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   /* text-align: center; */
   font-size: 16px;
  color: #707070;
  border-bottom: solid 2px #E2E5ED;
  width: 100vw;
  /* margin-top: 60px;  */
}


</style>
