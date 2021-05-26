<template>

  <main>
    <div>
      
    </div>
  </main>

</template>

<script>

  import axios from 'axios'
  export default {
    name:'MainComp',
    components:{
    },
    data(){
      return{
        apiURL:'https://api.themoviedb.org/3/search/movie',
        apiKey:'2ebbaf41573368f2518eaf78fad9226a',
        query:'marvel',
        cover:[]
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
      .then(resp => {
        console.log(resp.data.results);
      })
      .catch(err => {
        console.log(err);
      })
    }
  }    
  
</script>

<style>

</style>