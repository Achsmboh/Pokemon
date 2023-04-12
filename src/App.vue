<template>
  <NavbarMenu />
  <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
  
</template>

<script lang="ts">
import { defineComponent } from 'vue';
// import HelloWorld from './components/HelloWorld.vue';
import NavbarMenu from './components/Navbar.vue'

export default defineComponent({
  name: 'App',
  components: {
    // HelloWorld,
    NavbarMenu
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
body{
  margin: 0;
  padding: 0;
}
</style>
