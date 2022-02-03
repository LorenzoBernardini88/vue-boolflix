<template>
    <ul class="info_serie">
        <li>Titolo Originale: {{serie.original_name}}</li>
        <li>Titolo: {{serie.name}}</li>
        <li><img :src="flagLanguage()" alt=""></li>
        <li>Voto: {{serie.vote_average}}</li>
    </ul>
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
        }
    }
}
</script>

<style>

</style>