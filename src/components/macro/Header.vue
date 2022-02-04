<template>
    <header>
        <div class="head_cont">
            <img src="../../assets/img/boolflix_logo.png" alt="">
            <input-text @ricerca="trasmettiData"/>
        </div>
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
@import "../../assets/style/vars.scss";
header{
    background: $bg-head;
    padding: 10px 20px;
    .head_cont{
        display: flex;
        align-items:center;
        justify-content:space-between;
        img{
            width: 150px;
        }
    }
        
}
</style>
