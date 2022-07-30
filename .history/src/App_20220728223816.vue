<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
    <div id="main-flex">
      <div class="my-sidebar">
        <ul class="my-sidebar-items">
            <li class="sidebar-item-active"> <img src="./assets/video-player.png" alt=""> &nbsp; My Recordings</li>
            <li> <i class="fa fa-share-alt" style="color:#102346"></i> &nbsp; Requested</li>
        </ul>
      </div>
        <div class="my-main">
          <div class="my-main-container">
            <div><small style="color:#637C8E">Snapbyte <i class="fa fa-angle-right" style="font-weight:200"></i> My Recordings</small></div>
            <div class="subheading-tab">
              <div> My Recordings 25 </div>
              <div> 
                <button class="sub-heading-btn">By Date</button>
                <button class="sub-heading-btn">Add Filter</button>
                <button class="sub-heading-btn">New Request</button>
                <button class="sub-heading-btn">Start Recording</button>
              </div>
            </div>
          </div>
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
  width: 100%;
}

.my-sidebar {
  flex: 0 0 240px;
  /* width: 20%; */
  height: 100vh;
  background-color: #ebf2f656;
  border-right: 2px solid #21455e54;
  /* border-right: 2px solid #21455E; */
  /* width:250px; */
}
.my-sidebar-items {
  list-style: none;
  padding: 20px 0;
}
.my-sidebar-items>li {
  margin : 10px 12px 10px 18px;
  padding: 7px 20px ;
}
.sidebar-item-active {
  background-color: #E2E5ED;
  border: 2px solid #0DABD838;
  border-radius: 10px;
}





.my-main {
  flex: 1;
  flex-wrap: wrap;
}
.my-main-container {
  padding: 1.5% 8.5%;
}
.subheading-tab {
  display: flex;
  justify-content: space-between;
}
.sub-heading-btn {
  padding: 10px;
  border: 20px;
}



#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  font: normal normal normal 14px/26px Poppins;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   /* text-align: center; */
   font-size: 16px;
  color: #707070;
  border-bottom: solid 2px #E2E5ED;
  overflow: hidden;
  /* margin-top: 60px;  */
}


</style>
