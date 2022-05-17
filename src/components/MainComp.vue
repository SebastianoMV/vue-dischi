<template>
<main >
  <div class="container">
    <CardComp/>
  </div>
  
</main>
  
</template>

<script>
import CardComp from './CardComp.vue';
export default {
    name: "MainComp",
    components: { CardComp }
}
</script>

<style lang="scss" scoped>
main{
  height: calc(100vh - 50px);
  background-color: #1e2d3b;
}

</style>