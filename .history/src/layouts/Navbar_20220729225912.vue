<template>
    <nav class="">
      <div class="nav-logo-area">
        <div class="nav-logo-area-inner">
          <div class="white-logo-wrap">
            <span class="white-logo-bkg">
            <img alt="Adilo logo" src="../assets/swarm.png">
            </span>
          </div>
          <div class="adilo">Adilo</div>
        </div>
      </div>
      <div class="nav-tab">
        <ul class="my-nav-list">
          <li><a>Projects</a></li>
          <li class="my-btn active-nav-item dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"> <a>Tools & App</a></li>
          <li><a>Channels</a></li>
          <li><a>Contacts</a></li>
          <li><a>Analytics</a></li>
          <li><a>Settings</a></li>
        </ul>
      </div>
      <div class="nav-profile">
        <ul class="my-nav-list">
          <li><a><b>Help</b></a></li>
        </ul>
        <div class="profile-info">
          <div class="profile-border"></div>
          <div >
            <img alt="Profile Image" src="../assets/profile.jpg" class="profile-img">
          </div>
          <div style="margin-left:10px">
            <span class="profile-name">Ifeoluwa Olajide </span>
            <p class="profile-email">ifeoluwaolajide@gmail.com</p>
          </div>
        </div>
      </div>
      <!-- Example single danger button -->
<div class="btn-group">
  <button type="button" class="btn btn-danger dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Action
  </button>
  <div class="dropdown-menu">
    <a class="dropdown-item" href="#">Action</a>
    <a class="dropdown-item" href="#">Another action</a>
    <a class="dropdown-item" href="#">Something else here</a>
    <div class="dropdown-divider"></div>
    <a class="dropdown-item" href="#">Separated link</a>
  </div>
</div>
    </nav>
</template>
<script>
export default {
    name: 'NavbarComponent'
}
</script>
<style>
     nav {
    display: flex;
    /* height: 69px; */
    padding: 0 0.032%;
    border-bottom: solid 1px #E2E5ED;
  }

  .nav-logo-area {
    flex: 0 0 16%;
    padding-left: 3.2%;
    padding-top: 19px;
    padding-bottom: 27px;
  }
  .nav-logo-area-inner {
    display: flex;
  }
  .nav-tab {
    flex: 0 0 50%;
  }
  .nav-profile {
    flex: 0 0 34%;
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
    /* font: normal normal normal 18px/27px Poppins; */
    letter-spacing: 0px;
    color: #707070;
    opacity: 1
  }
  .white-logo-wrap {
    padding-top:16px;
  }
  .white-logo-bkg {     
    background-color:#FBBD71;
    padding:7px 4px;
    border-radius:10px;
  }
  .adilo {
    font: normal normal bold 28px/32px Helvetica;
    font-size:28px; 
    margin-left:15px; 
    font-weight:bold; 
    color:#21455E; 
    padding-top:14px;
  }
  .profile-info {
    padding-top:35px;
    display:flex;
  }
  .active-nav-item {
    border-top: 6px solid #0DABD8;
    font-weight: 600;
  }
  .profile-border {
    border-left: 1px solid #A3BAC6; 
    padding-left:25px; 
    height:40px;
  }
  .profile-img {
    width:45px; height: 45px; 
    border-radius:10px;
  }
  .profile-name {
    font-weight:bold; 
    font-size:15px; 
    color:black;
  }
  .profile-email {
    font-size:13px;
  }
</style>