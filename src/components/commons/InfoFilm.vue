<template>
    <div class="film_cont">
        <div class="cover_cont"><img :src="getCover('w342')+film.poster_path" alt=""></div>
        <ul class="info_film">
            <li class="title_original">Titolo Originale: {{film.original_title}}</li>
            <li class="title">Titolo: {{film.title}}</li>
            <li><img class="flag_img" :src="flagLanguage()" alt=""></li>
            <li><i v-for="(elemento,indice) in starArray" :key="indice" class="fas fa-star star_vote"></i></li>
        </ul>
    </div>
</template>
        

<script>
export default {
    name:'infoFilm',
    props:{
        film: Object,
        
    },
    data(){
        return{
            star:""
        }
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
        // getStar : function(){
        //     const voteArray = []
        //     this.star = (this.film.vote_average/2).toFixed(0)
        //     for (let index = 0; index < this.star; index++) {
        //         voteArray.push(this.star)
        //     }
        //         return voteArray
        // }

    },
    computed:{
        starArray(){
            const voteArray = []
            const star = (this.film.vote_average/2).toFixed(0)
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
.film_cont{
    width: 200px;
    position: relative;
    img{
        width: 200px;
        height: 100%;
    }
    ul{
        width: 200px;
        height: 100%;
        list-style-type: none ;
        background: $bg-head;
        color: white;
        font-size: 15px;
        position: absolute;
        top:0px;
        left: 0px;
        opacity: 0;

        &:hover{
            opacity: 1;
        }
    }
}
</style>

    
    
            
            
        
    





