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




    .my-container{
        margin: 0 6.5% ;
        overflow-x: hidden;
    }
    #main-flex{
        display: flex;
        justify-content: flex-start;
        height: 100%;
    }
    .my-sidebar{
        flex: 0 0 200px;
        height: 100%;
        /* width: 200px; */
    }
    .my-nav{
        box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
    }
    .my-nav>ul{
        list-style-type: none;
        display: block;
        padding: 0;
    }
    .my-nav>ul>li{
        display: block;
    }
    .active-temp{
        font-weight: 600;
    }
    .my-nav>ul>li:hover, .active-temp{
        cursor: pointer;
        background-color: rgb(241, 241, 241);
    }
    .my-nav>ul>li>a{
        color: #282828;
        padding: 5% 5% 5% 10%;
        display: block;
    }
    .my-nav>ul>li>a:hover{
        transform: scale(1.03);
        font-weight: 600;
    }
    .my-main{
        width: 100%;
    }
    @media screen and (max-width: 500px) {
        .my-main{
            flex-shrink: 0;
        }
    }
    .main-content{
        box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
    }
    /* .inner-main>div{
        flex: 1;
    } */

    .under-nav>a{
        display: block;
        padding: 10px 0 10px 22px;
    }

    .fade-enter-active {
        transition: all 0.5s ease-in-out;
    /* transition: all 0.3s ease-out; */
    }

    .fade-leave-active {
        transition: all 0.5s ease-in-out;
    /* transition: all 0.3s ; */
    }
    .fade-enter-from,
    .fade-leave-to {
    transform: translateX(15px);
    opacity: 0;
    }

    .fade-leave-active, .fade-enter-active .my-sidebar {
    transition-delay: 0.25s;
    }

    .u-hamburger__box:hover{
        cursor: pointer;
    }

    .pg-head{
        border-bottom: 1px solid rgb(230, 225, 225);
    }

    @media screen and (max-width: 900px) {
        .my-container{
            margin: 0 0 ;
        }
    }







</style>
