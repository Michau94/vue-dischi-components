<template>
  <div id="app">
    <Header :opt="options" @selectedOption="selected" />
    <Loader v-if="isLoading">
      <h1 class="text-light">Is Loading...</h1>
    </Loader>
    <main v-else>
      <Content :albums="albumList" :filtered="filteredAlbum" />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
import Loader from "./components/Loader.vue";

export default {
  name: "App",
  components: {
    Header,
    Content,
    Loader,
  },
  data() {
    return {
      albumList: [],
      currentOption: "all",
      isLoading: true,
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albumList = res.data.response;
        this.isLoading = false;
      });
  },
  methods: {
    selected(fil) {
      this.currentOption = fil;
    },
  },

  computed: {
    options() {
      let genres = [];
      this.albumList.forEach((song) => {
        if (!genres.includes(song.genre)) {
          genres.push(song.genre);
        }

        console.log(genres);
      });
      return genres;
    },

    filteredAlbum() {
      if (this.currentOption === "all") return this.albumList;

      let filtered = this.albumList.filter(
        (alb) => alb.genre === this.currentOption
      );

      let sorted = [...filtered];
      sorted.sort((a, b) => {
        return a.year - b.year;
      });
      return sorted;
    },
  },
};
</script>

<style lang="scss">
@import "./scss/style.scss";
</style>
