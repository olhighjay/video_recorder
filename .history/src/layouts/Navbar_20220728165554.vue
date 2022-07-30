<template>
    <nav class="">
      <div class="nav-logo-area">
        <div class="nav-logo-area-inner">
          <div class="white-logo-wrap">
            <span class="white-logo-bkg">
            <img alt="Adilo logo" src="./assets/swarm.png">
            </span>
          </div>
          <div class="adilo">Adilo</div>
        </div>
      </div>
      <div class="nav-tab">
        <ul class="my-nav-list">
          <li><a>Projects</a></li>
          <li class="active-nav-item"> <a>Tools & App</a></li>
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
        <div class="profile-info">
          <div class="profile-border"></div>
          <div >
            <img alt="Profile Image" src="./assets/profile.jpg" class="profile-img">
          </div>
          <div style="margin-left:10px">
            <span class="profile-name">Ifeoluwa Olajide </span>
            <p class="profile-email">ifeoluwaolajide@gmail.com</p>
          </div>
        </div>
      </div>
    </nav>
</template>
<script>
export default {
    name: 'NavbarComponent'
}
</script>