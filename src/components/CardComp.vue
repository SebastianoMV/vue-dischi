<template>
<div class="col my-3">
  <div class="smv-card d-flex flex-column  align-items-center p-2 text-center">
    <img :src="card.poster" :alt="card.poster" class="mt-2">
    <h4 class="my-2">{{card.title}}</h4>
    <p>{{card.author}}</p>
    <p>{{card.year}}</p>

  </div>
  
</div>
  
</template>

<script>


export default {
  name:'CardComp',
  props:{
    card: Object
  }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/var';
.smv-card{
  width: 100%;
  height: 400px;
  background-color: $primary-color;
  img{
    width: 90%;
  }
  h4{
    color: white;
  }
  p{
    color: gray;
  }
}

</style>