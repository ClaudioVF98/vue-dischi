<template>


  <div class="card">
    <img :src="musicObject.poster" :alt="musicObject.title">
    <h3>{{ musicObject.title }}</h3>
    <p>{{ musicObject.author }}</p>
    <p>{{ musicObject.year }}</p>
    <p>{{ musicObject.genre }}</p>
  </div>
</template>

<script>
export default {
  name: "MusicCard",
  props: {
    musicObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
  width: calc((100% / 5) - 20px);
  background-color: #2e3a46;
  margin: 10px;
  text-align: center;

  h3 {
    color: white;
  }

  img {
    width: 100%;
    height: 80%;
    object-fit: cover;
  }

  p {
    color: lightslategray;
  }
}
</style>