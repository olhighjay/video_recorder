<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div>
    <navbar></navbar>
    <div id="main-flex">
            <Transition name="fade" :duration="550">
                <div class="my-sidebar px-1">
                    <div class="my-nav py-4">
                        <ul>
                            <li :class="{'active-temp': pageHeader == 'Dashboard'}"><router-link style="width:100%" to="/dashboard"><i class="fa fa-home" aria-hidden="true"></i> &nbsp; Dashboard</router-link></li>
                            <li :class="{'active-temp': pageHeader == 'My Account'}"><router-link style="width:100%" to="/account"><i class="fa fa-user" aria-hidden="true"></i> &nbsp; My Account</router-link></li>
                       </ul>
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
