<template>
  <div id="app">
    <SearchBar/>
    <SingleImage
    v-bind:url='test'> 
    </SingleImage>
  </div>
</template>

<script>
import SingleImage from './components/SingleImage'
import SearchBar from './components/SearchBar'
import axios from 'axios'

const axiosconfig = {
  baseurl: 'http://api.giphy.com/v1/gifs/trending?api_key=rr0lC3pBzUuNytwdumVXkT8njgPd0pbQ',
  timeout: 30000,
};
let imageUrl = ''

export default {
  name: 'app',
  data() {
    return {
      test: {
        text: imageUrl,
        items: []
      }
    }
  },
  components: {
    SearchBar,
    SingleImage
  },
  created() {
        axios.get(axiosconfig.baseurl).then((response) => {
            console.log(response.data.data)
            imageUrl = response.data.data[0].embed_url
            console.log(imageUrl)
            this.test = imageUrl
            this.items = response.data.data
        })
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
