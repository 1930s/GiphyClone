<template>
  <div class="image">
    <br><br>
    <span v-for="item in items">
      <iframe width="360" height="202.5" frameBorder="0" class="giphy-embed" :src='item.embed_url'></iframe>
    </span>
  </div>
</template>

<script>  
export default {
  name: 'SingleImage',
  props: ['url', 'items'],
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
