<template>

  <div id="app">

    <HeaderComp 
                @searching="searching"
    />

    <MainComp
              v-if="results.movie.length > 0" type='movie' :list="results.movie"
    />
    <MainComp
              v-if="results.tv.length > 0" type='tv' :list="results.tv"
    />

    <h1 v-if="results.movie.length === 0 && results.tv.length === 0">Nessun risultato trovato</h1>
  </div>

</template>

<script>
  import HeaderComp from './components/HeaderComp.vue';
  import MainComp from './components/MainComp.vue'
  import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      apiURL:'https://api.themoviedb.org/3/search/',
      apiKey:'2ebbaf41573368f2518eaf78fad9226a',
      results:{
        'movie':[],
        'tv':[]
      }
    }
  },
  methods:{
    searching(valore){
      this.resetSearch()
      if(valore.type === 'all'){
        this.getAPI(valore.text,'movie');
        this.getAPI(valore.text,'tv');
      }else{
        this.getAPI(valore.text, valore.type);
      }
    },

    resetSearch(){
      this.results.movie = [];
      this.results.tv = [];
    },

    getAPI(query, type){
      if(query !== ''){
        axios.get(this.apiURL+type,{
          params:{
            api_key: this.apiKey,
            query: query,
            language: 'it-IT'
          }
        })
        .then(res => {
          this.results[type] = res.data.results;
          console.log(res.data.results+'qui');
        })
        .catch(err =>{
          console.log(err);
        })
      }
    }
  }
}
</script>

<style lang="scss">

  @import './assets/style/general.scss';

</style>