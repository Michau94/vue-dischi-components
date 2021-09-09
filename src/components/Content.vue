<template>
  <div>
    <div class="container">
      <div class="album row">
        <div
          class=" col col-xs-12 col-sm-6 col-md-4 col-lg-3"
          v-for="(album, index) in albumList"
          :key="index"
          @keyup="$emit('options', options)"
        >
          <AlbumCard
            :poster="album.poster"
            :title="album.title"
            :artist="album.author"
            :year="album.year"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumCard from "./AlbumCard.vue";
export default {
  name: "Content",
  components: {
    AlbumCard,
  },

  data() {
    return {
      albumList: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albumList = res.data.response;
      });
  },
};
</script>

<style scoped lang="scss">
.album {
  padding-top: 100px;
  color: #fff;
}
</style>
