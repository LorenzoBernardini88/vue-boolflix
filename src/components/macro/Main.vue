<template>
    <main>
        <InputText
        @ricerca="filtraData"/>
        <h1>Lista Film:</h1>
        <InfoFilm
        v-for="elemento in dataArrayFilm"
        :key="elemento.id"
        :film="elemento"/>
        <h1>Lista Serie:</h1>
        <InfoSerie
        v-for="elemento in dataArraySerie"
        :key="elemento.id"
        :serie="elemento"/>
    </main>
</template>

<script>
import axios from 'axios';
import InputText from "../commons/InputText.vue";
import InfoSerie from "../commons/InfoSerie.vue";
import InfoFilm from "../commons/InfoFilm.vue";
export default {
    name:'Main',
    components:{
        InputText,
        InfoFilm,
        InfoSerie
    },
    data(){
        return{
            apiUrlFilm:"https://api.themoviedb.org/3/search/movie",
            apiUrlSerie:"https://api.themoviedb.org/3/search/tv",
            dataArrayFilm:[],
            dataArraySerie:[],
            film: ""
        }
    },
    created(){
        // this.getFilm();
    },
    methods:{
        filtraData(valoreRicerca){
            this.film = valoreRicerca;
            this.getFilm();
            this.getSerie();
        },
        getFilm(){
            axios.get(this.apiUrlFilm, {
                params: {
                api_key:"77b419d801283a9b373f36475ac132b1",
                query: this.film
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
                    query: this.film
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
        
    },
    
}
        



</script>

<style lang='scss' scoped>


</style>