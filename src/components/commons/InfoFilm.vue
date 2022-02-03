<template>
    <ul class="info_film">
        <li>Titolo Originale: {{film.original_title}}</li>
        <li>Titolo: {{film.title}}</li>
        <li><img :src="getCover('w342')+film.poster_path" alt=""></li>
        <li><img :src="flagLanguage()" alt=""></li>
        <li>{{getStar()}}</li>
    </ul>
</template>

<script>
export default {
    name:'infoFilm',
    props:{
        film: Object
        
    },
    methods:{
        flagLanguage(){
            if(this.film.original_language == 'it'){
                return require("../../assets/img/flat_icon/italy.png")
            }else if(this.film.original_language == 'en'){
                return require("../../assets/img/flat_icon/united-kingdom.png")
            }else if(this.film.original_language == 'es'){
                return require("../../assets/img/flat_icon/spain.png")
            }else{
                return require("../../assets/img/flat_icon/saudi-arabia.png")
            }
        },
        getCover(size){
            return `https://image.tmdb.org/t/p/${size}`
            
        },
        getStar(){
            return(this.film.vote_average/2).toFixed(0)
            // for (let index = 0; index < this.vote_average; index++) {
                
            // }
        }
    }
}
        
</script>

            


<style lang='scss' scoped>

</style>

