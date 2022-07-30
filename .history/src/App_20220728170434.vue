<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
    <div id="main-flex">
            <Transition name="fade" :duration="550">
                <!-- <div :class="{'m-fadeOut':!showSidebar, 'm-fadeIn':showSidebar, 'show-display':navDelayIn, 'hide-display':navDelayOut}" class="my-sidebar"> -->
                <div v-if="!showSidebar" class="my-sidebar px-1">
                    <div class="my-nav py-4">
                        <ul>
                            <li :class="{'active-temp': pageHeader == 'Dashboard'}"><router-link style="width:100%" to="/dashboard"><i class="fa fa-home" aria-hidden="true"></i> &nbsp; Dashboard</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'My Account'}"><router-link style="width:100%" to="/account"><i class="fa fa-user" aria-hidden="true"></i> &nbsp; My Account</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'Inbox'}"><router-link style="width:100%" to="/inbox"><i class="fa fa-envelope" aria-hidden="true"></i> &nbsp; Inbox</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'Pending Reviews'}"><router-link style="width:100%" to="/"><i class="fa fa-ban" aria-hidden="true"></i> &nbsp; Pending Reviews</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'Laslas Coupon'}"><router-link style="width:100%" to="/"><i class="fa fa-gift" aria-hidden="true"></i> &nbsp; Laslas Coupon</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'Saved Items'}"><router-link style="width:100%" to="/"><i class="fa fa-heart" aria-hidden="true"></i> &nbsp; Saved Items</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'Recently Viewed'}"><router-link style="width:100%" to="/"><i class="fa fa-eye" aria-hidden="true"></i> &nbsp; Recently Viewed</router-link></li>
                        </ul>
                        <div class="under-nav">
                            <a>Details</a>
                            <a>Address Book</a>
                            <a>Change Password</a>
                            <a>Newsletter Pareferences</a>
                        </div>
                    </div>
                </div>
            </Transition>
            <div class="my-main px-2">
                <div class="main-content">
                    <div class="pg-head px-4 pt-4 pb-1">
                        <span @click="showSidebar = !showSidebar" class="u-hamburger__box"><span class="u-hamburger__inner"></span></span>
                        <span style=" margin-left:4%"><h4 style="display:inline; text-align:left;font-weight:600;">{{ pageHeader }}</h4></span>
                    </div>
                    <slot ></slot>
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
