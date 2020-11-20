<template>
  <div id="app" class='container'>
    <TestList
      heading='Play List'
      :info=info.data.streams
    />
    <VideoPlayer />
  </div>
</template>

<script>
import TestList from './components/TestList.vue'
import VideoPlayer from './components/VideoPlayer.vue'
import axios from 'axios'
import Vue from 'vue'
Vue.prototype.$http = axios

export default {
  name: 'App',
  components: {
    TestList,
    VideoPlayer
  },
  data: function ()  {
    return {
      info: null
    }
  },
  mounted: function () {
    axios
      .get('https://vpe-static.bamgrid.com/sample-files/take-home-exam/test-streams.json')
      .then(response => (this.info = response))
      console.log('Info:', this.info);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  margin: 25px;
}
</style>
