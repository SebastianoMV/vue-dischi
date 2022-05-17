<template>
<main >
  <div class="container p-5" v-if="loaded">
    <div class="row row-cols-xxl-5 row-cols-md-3 row-cols-sm-2 row-cols-1">
      <CardComp v-for="(card, index) in musicCards.response" :key="index" :card='card'/>
    </div>
    
  </div>
  <div v-else class="d-flex justify-content-center align-items-center">
    <div class="lds-ripple"><div></div><div></div></div>
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
       loaded: false,
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
          this.loaded=true;
        })
     }
    },
}
</script>

<style lang="scss" scoped>
main{
  min-height: calc(100vh - 50px);
  background-color: #1e2d3b;
  .d-flex{
    height: calc(100vh - 50px);
  }
}
.lds-ripple {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-ripple div {
  position: absolute;
  border: 4px solid #dfc;
  opacity: 1;
  border-radius: 50%;
  animation: lds-ripple 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
}
.lds-ripple div:nth-child(2) {
  animation-delay: -0.5s;
}
@keyframes lds-ripple {
  0% {
    top: 36px;
    left: 36px;
    width: 0;
    height: 0;
    opacity: 0;
  }
  4.9% {
    top: 36px;
    left: 36px;
    width: 0;
    height: 0;
    opacity: 0;
  }
  5% {
    top: 36px;
    left: 36px;
    width: 0;
    height: 0;
    opacity: 1;
  }
  100% {
    top: 0px;
    left: 0px;
    width: 72px;
    height: 72px;
    opacity: 0;
  }
}


</style>