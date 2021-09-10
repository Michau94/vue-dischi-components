<template>
  <div>
    <div class="container">
      <div class="album row">
        <div
          class=" col col-xs-12 col-sm-6 col-md-4 col-lg-3"
          v-for="(album, index) in filtered"
          :key="index"
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
import AlbumCard from "./AlbumCard.vue";
export default {
  name: "Content",
  components: {
    AlbumCard,
  },
  props: ["albums", "filtered"],

  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
.album {
  padding-top: 100px;
  color: #fff;
}
</style>
