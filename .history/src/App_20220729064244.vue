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
            <div><small class="breadcrumbs">Snapbyte <i class="fa fa-angle-right" style="font-weight:200"></i> My Recordings</small></div>
            <div class="subheading-tab">
              <div> <span class="my-recordings">My Recordings </span><span class="my-recordings-count">25</span> </div>
              <div> 
                <button class="sub-heading-btn white-btn">By Date</button>
                <button class="sub-heading-btn white-btn">Add Filter</button>
                <button class="sub-heading-btn blue-btn">New Request</button>
                <button class="sub-heading-btn red-btn">Start Recording</button>
              </div>
            </div>
            <!-- <div style="border: 1px dashed #A3BAC6; margin-top:30px;
              border-radius: 38px;
              opacity: 1; padding-top:105.9px; padding-bottom:68.5px">
              <p style="color: #000; font-size: 22px; text-align:center; font-weight:medium; margin-top:56px">Say hello to the world!</p>
              <p style="color: #637C8E; font-size: 14px; text-align:center;">Record your first video/audio and share it what your team, friends, <br />followers and customers.</p>
              <div class="text-center">
                <button class="sub-heading-btn red-btn">Start Recording</button>
                <button class="sub-heading-btn blue-btn">New Request</button>
              </div>
            </div>
            <div class="footer" style="margin-top:42px; margin-bottom: 140px">
              <div>
                
              </div>
              <div>
                <p style="font-size: 26px; color:#21455E">Want more controls & better <br />quality recording?</p>
                <button class="sub-heading-btn blue-btn">Download the desktop recorder</button>
              </div>
            </div> -->
            <div class="table-responsive-xl" style="margin-top:46.1px">
              <table class="">
  <thead>
    <tr >
      <th scope="col" class="my-table-title">Recordings</th>
      <th scope="col" class="my-table-title" colspan="3">Title</th>
      <th scope="col" style="width:10%"></th>
      <th scope="col" class="my-table-title">Views</th>
      <th scope="col" class="my-table-title">Size</th>
      <th scope="col" class="my-table-title">Last Modified</th>
      <th scope="col" class="my-table-title"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="width:10%">
        <img alt="Profile Image" src="./assets/profile.jpg" style="width:100%; height:45px; border:10px">
      </td>
      <td style="width:30%" colspan="3">
        <span>Getting it right the first time </span> <br />
        <span>The Video description is shown here if the user has added it. </span>
      </td>
      <td style="width:10%">
      </td>
      <td>424</td>
      <td>923 KB</td>
      <td>3 months ago</td>
      <td><i class="fa fa-ellipsis-v"></i></td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
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
 @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;700&display=swap');

#main-flex {
  display: flex;
  width: 100%;
}

.my-sidebar {
  flex: 0 0 240px;
  /* width: 20%; */
  /* height: 100%; */
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
  padding: 3px 15px;
  border-radius: 20px;
  margin-left: 15px;
  font-size: 14px;
}
.white-btn {
  border: 1px solid #E2E5ED;
  background-color: white;
  color: #637C8E;
}
.blue-btn {
  border: none;
  background-color: #0DABD8;
  color: #fff;
}
.red-btn {
  border: none;
  background-color: #EF5350;
  color: #fff;
}
.my-recordings, .my-recordings-count {
  font-size: 24px;
  color: #000
}
.my-recordings {
  color: #000
}
.my-recordings-count {
  color: #637C8E;
  font-weight: 600;
}
.breadcrumbs {
  color:#637C8E;
}


table  {
  border-spacing: 300px !important;
}
th, td {
  padding: 15px;
}
.my-table-title {
  text-align: left;
  font: normal normal medium 18px/27px Poppins;
  letter-spacing: 0px;
  color: #21455E;
}



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
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
