<template>
  <div id="app">
    <Header @filtraData="dataApiApp"/>
    <Main :dataFilm="dataArrayFilm" :dataSerie="dataArraySerie"/>
  </div>
</template>


<script>
import axios from "axios"
import Header from "./components/macro/Header.vue"
import Main from "./components/macro/Main.vue"
export default {
  name: 'App',
  data(){
    return{
      apiUrlFilm:"https://api.themoviedb.org/3/search/movie",
      apiUrlSerie:"https://api.themoviedb.org/3/search/tv",
      inputTextApp:"",
      dataArrayFilm:[],
      dataArraySerie:[],
    }
  },
  components:{
    Main,
    Header
  },methods:{
    dataApiApp(filtroInput){
      this.inputTextApp = filtroInput
      this.getFilm(),
      this.getSerie()

    },
    getFilm(){
            axios.get(this.apiUrlFilm, {
                params: {
                api_key:"77b419d801283a9b373f36475ac132b1",
                query: this.inputTextApp
                }
            })
            .then((risposta)=> {
                this.dataArrayFilm = risposta.data.results;
                console.log(this.dataArrayFilm);
                
            })
            .catch(function (error) {
                console.log(error);
            })
        },
        getSerie(){
            axios.get(this.apiUrlSerie, {
                    params: {
                    api_key:"77b419d801283a9b373f36475ac132b1",
                    query: this.inputTextApp
                    }
                })
                .then((risposta)=> {
                    this.dataArraySerie = risposta.data.results;
                    console.log(this.dataArraySerie);
                    
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
        
  }

}
  
</script>

<style lang="scss">
@import "./assets/global.scss";
</style>
