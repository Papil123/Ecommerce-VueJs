<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>
     <div class="navbar"  > 
      <div><RouterLink to="/">Home</RouterLink></div>
      <div><RouterLink to="/about">About</RouterLink></div>
      </div>

      <RouterView />
  </div>
 
</template>

<style scoped>
  .navbar{
    display: flex;
    justify-content: space-around;
    width: 80%;
    /* border: 1px solid gray; */
  }
</style>
