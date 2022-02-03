<template>
    <ul class="info_film">
        <li>Titolo Originale: {{info.original_title}}</li>
        <li>Titolo: {{info.title}}</li>
        <li>Lingua: <img :src="flagLanguage()" alt=""></li>
        <li>Voto: {{info.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    name:'InfoFilm',
    props:{
        info: Object
        
    },
    methods:{
        flagLanguage(){
            if(this.info.original_language == 'it'){
                return require("../../assets/img/flat_icon/italy.png")
            }else if(this.info.original_language == 'en'){
                return require("../../assets/img/flat_icon/united-kingdom.png")
            }else if(this.info.original_language == 'es'){
                return require("../../assets/img/flat_icon/spain.png")
            }else{
                return require("../../assets/img/flat_icon/saudi-arabia.png")
            }
        }
    }
}
</script>

            


<style lang='scss' scoped>

</style>

