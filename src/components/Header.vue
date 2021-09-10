<template>
  <header>
    <div class="container">
      <img class="img-fluid" src="../assets/images/logo.png" alt="Logo" />
      <select
        name="filter"
        v-model="actualFilter"
        @change="$emit('selectedOption', actualFilter)"
      >
        <option value="all">All</option>
        <option v-for="(option, ind) in opt" :value="option" :key="ind">
          {{ option }}</option
        >
      </select>
    </div>
  </header>
</template>

<script>
export default {
  Name: "Header",
  props: ["opt"],
  data() {
    return {
      actualFilter: "all",
    };
  },
};
</script>

<style scoped lang="scss">
header {
  height: 80px;
  background-color: #2e3a46;

  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1;

  .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
  }

  img {
    height: 50px;
    vertical-align: middle;
  }
}
</style>
