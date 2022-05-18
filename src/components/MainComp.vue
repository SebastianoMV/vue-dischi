<template>
<main >
  <nav class="d-flex justify-content-between">
    <img src="https://www.geekslab.it/wp-content/uploads/2019/03/logo-spotify.png" alt="">
    <InputComp @filterGenre="recivedValue" />

  </nav>
  <div class="container p-5" v-if="loaded">
    <div class="row row-cols-xxl-5 row-cols-md-3 row-cols-sm-2 row-cols-1">
      <CardComp v-for="(card, index) in filtGenreArr" :key="index" :card='card'/>
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
import InputComp from './InputComp.vue';

export default {
    name: "MainComp",
    components: { CardComp, InputComp },

    data(){
      return{
       loaded: false,
       apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
       musicCards:[],
       stringToGenre:'',
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
          this.musicCards = response.data.response;
          console.log(this.musicCards);
          this.loaded=true;
        })
     },
     recivedValue(selectValue){
       
       this.stringToGenre = selectValue;
       console.log(this.stringToGenre);
     }
    },
    computed:{
      filtGenreArr(){
        let genreArr = [];
        if(this.stringToGenre.length == 0){
          genreArr = this.musicCards;
        }
        else if(this.stringToGenre == 'Tutti i generi'){
          genreArr = this.musicCards;
        }else{
          genreArr = this.musicCards.filter(cardgenre=> {
            return cardgenre.genre.toLowerCase().includes(this.stringToGenre.toLowerCase())
          })
        }
        return genreArr;
      }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/var';

main{
  min-height: 100vh;
  background-color: #1e2d3b;
  .d-flex{
    height: 100vh;
  }
  nav{
  max-height: 50px;
  padding: 10px;
  background-color: $primary-color;
  i{
    color: green;
  }
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