<template>
    <header>
        <img src="" alt="">
        <input-text @ricerca="trasmettiData"/>
    </header>
</template>

<script>
import InputText from '../commons/InputText.vue'
export default {
    name :'Header',
    components:{
        InputText
    },
    methods:{
        trasmettiData(inputFiltro){
            this.$emit('filtraData',inputFiltro)
        }
    }
}
</script>

<style lang='scss' scoped>

</style>
