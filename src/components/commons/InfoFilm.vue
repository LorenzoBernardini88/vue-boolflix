<template>
    <div class="film_cont">
        <div class="cover_cont"><img :src="getCover('w342')" alt=""></div>
        <ul class="info_film">
            <li class="title_original">Titolo Originale: {{film.original_title}}</li>
            <li class="title">Titolo: {{film.title}}</li>
            <li><img class="flag_img" :src="flagLanguage()" alt=""></li>
            <li><i v-for="elemento in getStar(star)" :key="elemento.id" class="fas fa-star star_vote"></i>
                <i v-for="elemento in (5-getStar(star))" :key="elemento.id" class="far fa-star star_vote"></i>
            </li>
            <li>Descrizione: {{film.overview}}</li>
            
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
            if(this.film.poster_path==null){
                console.log('ciao')
                return require("../../assets/img/no_cover.png")
            }else{
            return `https://image.tmdb.org/t/p/${size}`+ this.film.poster_path
            }
        },
        getStar(){
            this.star= Math.ceil(this.film.vote_average/2)
            return this.star
        }
    }
        


            
    // computed:{
    //     starArray(){
    //         const voteArray = []
    //         const star = (this.film.vote_average/2).toFixed(0)
    //         for (let index = 0; index < star; index++) {
    //             voteArray.push(star)
    //         }
    //             return voteArray
    //     }
    // }
}
</script>
            
<style lang='scss' scoped>
@import "../../assets/style/vars.scss";
.film_cont{
    width: 200px;
    height: 300px;
    position: relative;
    border-radius:10px;
    overflow: hidden;
    .cover_cont{
        border-radius:10px;
        width: 200px;
        height: 300px;
        img{
            border-radius:10px;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
            
    }
    ul{
        width: 200px;
        height: 100%;
        border-radius:10px; 
        list-style-type: none ;
        background: $bg-head;
        color: #ffffff;
        font-size: 15px;
        position: absolute;
        top:0px;
        left: 0px;
        opacity: 0;
        transition: opacity linear 0.5s;
        overflow-y:scroll;
            &::-webkit-scrollbar {
            -webkit-appearance: none;
            }
            &:hover{
                opacity: 1;
            }
        }
        .flag_img{
            width: 16px;
            
        }
    }

</style>





