<template>

  <main>
    <CoverComp />
  </main>

</template>

<script>

  import CoverComp from '../components/CoverComp.vue'

  export default {
    name:'MainComp',
    components:{
      CoverComp
    }
  }    
  
</script>

<style lang='scss' scoped>

  main{
    height: calc(100vh - 70px);
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    align-items: center;
    padding: 10px;
  }

</style>