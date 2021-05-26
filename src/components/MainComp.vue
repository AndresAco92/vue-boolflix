<template>

  <main>
    <CoverComp
                v-for="(cover) in films"
                :key='cover.id'
                :Covers = cover
    />
  </main>

</template>

<script>

  import axios from 'axios'
  import CoverComp from '../components/CoverComp.vue'

  export default {
    name:'MainComp',
    components:{
      CoverComp,
    },
    data(){
      return{
        apiURL:'https://api.themoviedb.org/3/search/movie',
        apiKey:'2ebbaf41573368f2518eaf78fad9226a',
        query:'marvel',
        films:[]
      }
    },
    mounted(){
      axios.get(this.apiURL,{
        params:{
          api_key: this.apiKey,
          query: this.query,
          language:'it-IT'
        }
      })
      .then(res => {
        this.films = res.data.results;
        console.log(res.data.results);
      })
      .catch(err => {
        console.log(err);
      })
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