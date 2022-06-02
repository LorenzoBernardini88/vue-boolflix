<template>
    <main>
        <div v-if="dataFilm ==0 && dataSerie ==0 " class="intro">
            <h1>Boolfix</h1>
        </div>
        <div v-else>
            <h1 >Film</h1>
            <div class="container">
                <InfoFilm
                v-for="elemento in dataFilm"
                :key="elemento.id"
                :film="elemento"/>
            </div>
            <h1>Serie TV</h1>
            <div class="container">
                <InfoSerie
                v-for="elemento in dataSerie"
                :key="elemento.id"
                :serie="elemento"/>
            </div>
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
.intro{
    width: 100%;
    height: 100vh;
    background-color: $bg-body;
    color: #CED5D5;
    // text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.container{
    width: 90%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap:10px;
}
h1{
    color:#DC1A28;
    text-align: center;
    margin: 20px 0px;
    font-size: 50px;
}

</style>