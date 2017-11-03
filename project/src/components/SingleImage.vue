<template>
  <div class="image">
    <br><br>
    <iframe width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen :src='url'></iframe>
  </div>
</template>

<script>  
export default {
  name: 'SingleImage',
  props: ['url'],
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
