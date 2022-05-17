<template>
<main >
  <div class="container p-5">
    <div class="row row-cols-5">
      <CardComp v-for="(card, index) in musicCards.response" :key="index" :card='card'/>
    </div>
    
  </div>
  
</main>
  
</template>

<script>
import CardComp from './CardComp.vue';
import axios from 'axios';

export default {
    name: "MainComp",
    components: { CardComp },

    data(){
      return{
       apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
       musicCards:[]
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
          this.musicCards = response.data;
          console.log(this.musicCards);
        })
     }
    },
}
</script>

<style lang="scss" scoped>
main{
  min-height: calc(100vh - 50px);
  background-color: #1e2d3b;
}

</style>