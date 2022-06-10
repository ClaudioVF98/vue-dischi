<template>
  <div class="header">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
  </div>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .header {
        background-color: #2e3a46;
        img {
            width: 2%;
            margin: 10px;
        }
    }
    
</style>
