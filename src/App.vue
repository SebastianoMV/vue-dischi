<template>
  <div>
   <HaderComp/>
   <MainComp/>
  </div>
</template>

<script>
import MainComp from './components/MainComp.vue';
import HaderComp from './components/HaderComp.vue';



export default {
  name: 'App',
  components: {
    MainComp,
    HaderComp
}
}
</script>

<style lang="scss">
@import './assets/style/general'


</style>
