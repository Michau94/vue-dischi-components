<template>
  <header>
    <div class="container">
      <img class="img-fluid" src="../assets/images/logo.png" alt="Logo" />
      <select name="filter">
        <option value="all">All</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  Name: "Header",
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
