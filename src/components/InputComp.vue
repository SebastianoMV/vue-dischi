<template>
  <select v-model="selected" class="form-select m-2" aria-label="Default select example" @change="$emit('filterGenre', selected)">
    <option value="">Tutti i generi</option>
    <option  v-for="(genre,index) in arrGenre" :key="index">{{genre}}</option>
    
</select>
</template>

<script>
export default {
  name :'InputComp',
  data() {
    return {
      selected:''
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