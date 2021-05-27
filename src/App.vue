<template>

  <div id="app">

    <HeaderComp 
                @searching="searching"
    />

    <MainComp />

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
      apiUrl:'https://api.themoviedb.org/3/search/',
      apiKey:'2ebbaf41573368f2518eaf78fad9226a'
    }
  },
  methods:{
    searching(valore){
      if(valore.type === 'all'){
        this.getAPI(valore.text,'movie');
        this.getAPI(valore.text,'movie');
      }else{
        this.getAPI(valore.text,valore.type);
        
      }
    }

    getAPI(query, type){
      axios.get(this.apiUrl+type,{
        paramas:{
          api_key: this.apiKey,
          query: query,
          language: 'it-IT'
        }
      })
      .then(res => {
        console.log(res.data.results);
      })
      .catch(err =>{
        console.log(err);
      })
    }
  }
}
</script>

<style lang="scss">

  @import './assets/style/general.scss';

</style>