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
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
iframe {
  margin: 1em 1em;
}
</style>
