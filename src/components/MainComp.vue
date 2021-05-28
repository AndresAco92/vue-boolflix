<template>

  <main>
    <div class="container">
      <h1>{{titles[type]}}</h1>

      <CoverComp
                v-for="card in list"
                :key="card.id"
                :card='card'
      />     
    </div>

  </main>

</template>

<script>

  import CoverComp from '../components/CoverComp.vue'

  export default {
    name:'MainComp',
    components:{
      CoverComp
    },
    props:{
      type: String,
      list: Array
    },
    data(){
      return{
        titles:{
          'movies': 'Film trovati',
          'tv': 'Serie tv trovate'
        }
      }
    }
  }    
  
</script>

<style lang='scss' scoped>

  main{
    height: calc(100vh - 70px);
    display: flex;
    justify-content: center;
    align-items: center;
    .container{
      width: 90%;
      height: 90%;
    }
  }

</style>