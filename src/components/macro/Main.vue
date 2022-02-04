<template>
    <main>
        
        <h1>Lista Film:</h1>
        <InfoFilm
        v-for="elemento in dataFilm"
        :key="elemento.id"
        :film="elemento"/>
        <h1>Lista Serie:</h1>
        <InfoSerie
        v-for="elemento in dataSerie"
        :key="elemento.id"
        :serie="elemento"/>
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
        dataFilm:Object,
        dataSerie:Object
    },
    methods:{
        
        
    },
    
}
        



</script>

<style lang='scss' scoped>


</style>