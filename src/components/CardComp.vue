<template>
<div>
  cards
</div>
  
</template>

<script>
import axios from 'axios';

export default {
  name:'CardComp',
  data(){
    return{
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music'
    }
  },
  mounted() {
    this.getApi();
  },
  methods: {
    getApi(){
      axios.get(this.apiUrl)
      .then(response => {
        console.log(response.data);
      })
    }
  },

}
</script>

<style lang="scss" scoped>

</style>