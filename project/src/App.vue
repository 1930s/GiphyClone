<template>
  <div id="app">
    <SearchBar v-on:message='getKeywordImages'>
    </SearchBar>
    <SingleImage
    v-bind:items='items'> 
    </SingleImage>
  </div>
</template>

<script>
import SingleImage from './components/SingleImage'
import SearchBar from './components/SearchBar'
import axios from 'axios'

const axiosconfig = {
  baseurl: 'http://api.giphy.com/v1/gifs/trending?api_key=rr0lC3pBzUuNytwdumVXkT8njgPd0pbQ',
  searchurl: 'http://api.giphy.com/v1/gifs/search?api_key=rr0lC3pBzUuNytwdumVXkT8njgPd0pbQ&q=',
  timeout: 30000,
};


export default {
  name: 'app',
  data() {
    return {
        test: '',
        items: [],
    }
  },
  methods: {
    getKeywordImages: function(keyword) {
      axios.get(axiosconfig.searchurl + keyword).then((response) => {
            this.items = response.data.data
        })
    }
  },
  components: {
    SearchBar,
    SingleImage
  },
  created() {
        axios.get(axiosconfig.baseurl).then((response) => {
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
body {
  background-color: #274555;
}
</style>
