<template>
  <div class="search">
    <input v-model="message" placeholder="edit me">
    <button v-on:click="clickedSearch">Search</button>
    <p>{{ message }}</p>
  </div>
</template>

<script>
  
export default {
  name: 'SearchBar',
  data () {
    return {
      message: ''
    }
  },
  methods: {
    clickedSearch: function(event) {
      this.$emit('message', this.message)
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
