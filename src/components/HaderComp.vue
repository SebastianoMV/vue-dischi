<template>
  <nav class="d-flex justify-content-between">
    <img src="https://www.geekslab.it/wp-content/uploads/2019/03/logo-spotify.png" alt="">
    <select name="genere" id="genere" multiple>
      <option value=""></option>
      <option value=""></option>
      <option value=""></option>
    </select>

  </nav>
</template>

<script>
export default {
  name:'HeaderComp'
}
</script>

<style lang="scss" scoped>
@import '../assets/style/var';
nav{
  height: 50px;
  padding: 10px;
  background-color: $primary-color;
  i{
    color: green;
  }
}

</style>