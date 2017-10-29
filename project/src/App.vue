<template>
  <div id="app">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import axios from 'axios'

const axiosconfig = {
  baseurl: 'http://api.giphy.com/v1/gifs/trending?api_key=rr0lC3pBzUuNytwdumVXkT8njgPd0pbQ',
  timeout: 30000,
};
let imageUrl = ''

axios.get(axiosconfig.baseurl).then((response) => {
    console.log(response)
    imageUrl = response.data.data[0].url
    console.log(imageUrl)
})

export default {
  name: 'app',
  components: {
    HelloWorld
  }
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
