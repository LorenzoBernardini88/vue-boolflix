<template>
    <main>
        <InputText
        @ricerca="filtraData"/>
    </main>
</template>

<script>
import axios from 'axios';
import InputText from "../commons/InputText.vue";
export default {
    name:'Main',
    components:{
        InputText
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