<template>
  <select v-model="selected" class="form-select" aria-label="Default select example" @change="$emit('filterGenre', selected)">
    <option selected>Tutti i generi</option>
    <option  v-for="(genre,index) in arrGenre" :key="index">{{genre}}</option>
    
</select>
</template>

<script>
export default {
  name :'InputComp',
  data() {
    return {
      selected:'Tutti i generi'
    }
  },
  props:{
    arrGenre : Array
  }
};
</script>

<style lang="scss" scoped>
.form-select{
  width: 200px;
  padding: 2px;
}

</style>