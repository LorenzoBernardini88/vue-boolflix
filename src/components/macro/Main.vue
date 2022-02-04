<template>
    <main>
        <h1>Lista Film:</h1>
        <div class="container">
            <InfoFilm
            v-for="elemento in dataFilm"
            :key="elemento.id"
            :film="elemento"/>
        </div>
        <h1>Lista Serie:</h1>
        <div class="container">
            <InfoSerie
            v-for="elemento in dataSerie"
            :key="elemento.id"
            :serie="elemento"/>
        </div>
    </main>
</template>
        

<script>
import InfoSerie from "../commons/InfoSerie.vue";
import InfoFilm from "../commons/InfoFilm.vue";
export default {
    name:'Main',
    components:{
        InfoFilm,
        InfoSerie
    },
    props:{
        dataFilm:Array,
        dataSerie:Array
    },
}
</script>
    
    
<style lang='scss' scoped>
@import "../../assets/style/vars.scss";
.container{
    width: 90%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap:10px;
}



</style>




