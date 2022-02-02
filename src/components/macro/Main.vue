<template>
    <main>
        <InputText/>
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
            dataArray:[]
        }
    },
    created(){
        this.getFilm();
    },
    methods:{
        getFilm(){
            axios.get(this.apiUrl, {
                params: {
                api_key:"77b419d801283a9b373f36475ac132b1",
                query: 'zorro'
                }
            })
        .then((risposta)=> {
            this.dataArray = risposta.data.results;
            console.log(this.dataArray);
        })
        .catch(function (error) {
            console.log(error);
        })
        }
    }
}
</script>

<style lang='scss' scoped>

</style>