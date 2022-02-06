<template>
    <div class="serie_cont">
        <div class="cover_cont"><img :src="getCover('w342')" alt=""></div>
        <ul class="info_serie">
            <li class="title_original">Titolo Originale: {{serie.original_name}}</li>
            <li class="title">Titolo: {{serie.name}}</li>
            <li ><img class="flag_img" :src="flagLanguage()" alt=""></li>
            <li ><i v-for="(elemento,indice) in starArray" :key="indice" class="fas fa-star star_vote"></i></li>
        </ul>
    </div>
        
</template>

<script>
export default {
    name:'infoSerie',
    props:{
        serie: Object
        
    },
    methods:{
        flagLanguage(){
            if(this.serie.original_language == 'it'){
                return require("../../assets/img/flat_icon/italy.png")
            }else if(this.serie.original_language == 'en'){
                return require("../../assets/img/flat_icon/united-kingdom.png")
            }else if(this.serie.original_language == 'es'){
                return require("../../assets/img/flat_icon/spain.png")
            }else{
                return require("../../assets/img/flat_icon/saudi-arabia.png")
            }
        },
        getCover(size){
            if(this.serie.poster_path==null){
                console.log('ciao')
                return require("../../assets/img/no_cover.png")
            }else{
            return `https://image.tmdb.org/t/p/${size}`+ this.serie.poster_path
            }
            
        }
    },
    computed:{
        starArray(){
            const voteArray = []
            const star = (this.serie.vote_average/2).toFixed(0)
            for (let index = 0; index < star; index++) {
                voteArray.push(star)
            }
                return voteArray
        }
    }
}
</script>

<style lang='scss' scoped>
@import "../../assets/style/vars.scss";

</style>