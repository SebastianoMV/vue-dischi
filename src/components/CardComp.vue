<template>
<div class="col my-3">
  <div class="smv-card">
    <div class="flip-card-inner">
      <div class="flip-card-front">
        <img :src="card.poster" :alt="card.poster" class="mt-2">
        <h4 class="my-2">{{card.title}}</h4>
        <p>{{card.author}}</p>
        <p>{{card.year}}</p>
      </div>
      <div class="flip-card-back">
        <h4>{{card.title}}</h4>
        <p>{{card.author}}</p>
        <p>{{card.year}}</p>
        <p>{{card.genre}}</p>
      </div>
    </div>
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
  min-height: 400px;
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
// Flip

.flip-card-inner {
  position: relative;
  min-width: 100%;
  min-height: 400px;
  max-height: 600px;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  background-color: $primary-color !important;
}

.smv-card:hover .flip-card-inner {
  transform: rotateY(180deg);
  background-color: $primary-color;
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  min-height: 400px;
  backface-visibility: hidden;
  background-color: $primary-color;
 
}

.flip-card-back {
  transform: rotateY(180deg);
  background-color: lighten($primary-color, $amount: 10%);
  h4{
    color: darken($primary-color, $amount: 15%);
    text-transform: uppercase;
  }
   p{
    color: darken($primary-color, $amount: 15%);
    font-size: 20px;
    font-weight: 500;
  }
}


</style>