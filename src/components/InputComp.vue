<template>
  <select v-model="selected" class="form-select" aria-label="Default select example" @change="$emit('filterGenre', selected)">
    <option>Tutti i generi</option>
    <option>Rock</option>
    <option>Jazz</option>
    <option>Pop</option>
    <option>Metal</option>
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
};
</script>

<style lang="scss" scoped>
.form-select{
  width: 200px;
  padding: 2px;
}

</style>