<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
import $ from 'jquery'
export default {
  name: 'App',
  mounted () {
    function initScreen () {
      $('html').css('font-size', document.documentElement.clientWidth / 750 * 625 + '%')
      console.log($('html').css('font-size'))
    }
    (function () {
      setTimeout(function () {
        initScreen()
        window.addEventListener('onorientationchange' in window ? 'orientationchange' : 'resize', function (e) { initScreen(e) }, false)
        //  监测页面宽度的改变和横竖屏的变化，变化则调用initScreen
      }, 100)
    })()
  }
}
</script>

<style>
  html{
    font-size: 625%;
  }
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
*{
    padding: 0;
    margin: 0;
  }
</style>
