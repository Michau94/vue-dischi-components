<template>
  <div class="card">
    <img :src="poster" :alt="title" />
    <h2 class="title">{{ title }}</h2>
    <address class="artist">{{ artist }}</address>
    <time class="year"> {{ year }} </time>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: ["title", "artist", "year", "poster"],
};
</script>

<style lang="scss" scoped>
.card {
  text-align: center;

  border: 1px solid black;
  margin: 20px;
  padding: 15px;
  background-color: #2e3a46;
  border-radius: 10px;
  box-shadow: 5px 2px rgba(0, 0, 0, 0.5);
  height: 450px;

  img {
    width: 100%;
  }
  .title {
    margin: 15px 0;
    text-transform: uppercase;
  }
  .artist,
  .year {
    font-style: normal;
    color: #808080;
    font-size: 20px;
  }
  .card .year {
    font-size: 15px;
  }
}
</style>
