<template>
    <main>
        <InputText
        @ricerca="filtraData"/>
        <InfoFilm
        v-for="(elemento,indice) in dataArray"
        :key="indice"
        :info="elemento"/>
    </main>
</template>

<script>
import axios from 'axios';
import InputText from "../commons/InputText.vue";
import InfoFilm from "../commons/InfoFilm.vue";
export default {
    name:'Main',
    components:{
        InputText,
        InfoFilm
    },
    data(){
        return{
            apiUrl:"https://api.themoviedb.org/3/search/movie",
            dataArray:[],
            film: ""
        }
    },
    created(){
        // this.getFilm();
    },
    methods:{
        getFilm(){
            axios.get(this.apiUrl, {
                params: {
                api_key:"77b419d801283a9b373f36475ac132b1",
                query: this.film
                }
            })
            .then((risposta)=> {
                this.dataArray = risposta.data.results;
                console.log(this.dataArray);
                
            })
            .catch(function (error) {
                console.log(error);
            })
        },
        filtraData(valoreRicerca){
            this.film = valoreRicerca;
            this.getFilm();
        }
        
    },
    
}
</script>

<style lang='scss' scoped>

</style>