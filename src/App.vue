<template>
  <div id="app">
    <img src="./assets/logo.png">

    <router-link :to="{name:'Home'}">Home </router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/weather/WX4FBXXFKE4F">BeiJing</router-link>
    <router-link to="/weather/WTW3SJ5ZBJUY">ShangHai</router-link>
    <router-link to="/weather/WS0E9D8WN298">GuangZhou</router-link>

    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
