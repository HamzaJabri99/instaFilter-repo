<template>
  <div id="app" class="flexbox flexdir-col">
   <Navbar></Navbar>
   <MainContainer/>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
  </div>
</template>
<script>
import Navbar from './components/navbar/Navbar.vue';
import MainContainer from './components/main/MainContainer.vue';
export default {
  name:'app',
  components:{
   Navbar,
  MainContainer
  }
}
</script>
<style>
@import './assets/css/flexbox-util.css';
@import './assets/css/main.css';

#app
{
  height: 100%;
}
</style>
