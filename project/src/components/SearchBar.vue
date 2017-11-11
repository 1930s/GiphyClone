<template>
  <div class="search">
    <input v-model="message" id='text' placeholder="Search">
    <button id="btn" v-on:click="clickedSearch">&#8595;</button>
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

input {
  border: 0;
  outline: 0;
  background: transparent;
  border-bottom: 3px solid #ff7761;
  font-size: 18pt;
  color: #fff;
}

button {
  border: 0;
  outline: 0;
  background: transparent;
  font-size: 18pt;
  color: #fff;
  font-weight: bold;
  cursor: pointer;
}

::-webkit-input-placeholder { /* Chrome/Opera/Safari */
  color: white;
}
::-moz-placeholder { /* Firefox 19+ */
  color: white;
}
:-ms-input-placeholder { /* IE 10+ */
  color: white;
}
:-moz-placeholder { /* Firefox 18- */
  color: white;
}
</style>
