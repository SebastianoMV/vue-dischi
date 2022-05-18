<template>
  <select v-model="selectedAuthor" class="form-select" aria-label="Default select example" @change="$emit('filterGenre', selectedAuthor)">
    <option selected>Tutti gli artisti</option>
    <option  v-for="(artist,index) in arrArtists" :key="index">{{artist}}</option>
    
</select>
</template>

<script>
export default {
  name :'SelectArtists',
  data() {
    return {
      selectedAuthor:'Tutti gli artisti'
    }
  },
  props:{
    arrArtists : Array
  }
};
</script>

<style lang="scss" scoped>
.form-select{
  width: 200px;
  padding: 2px;
}

</style>