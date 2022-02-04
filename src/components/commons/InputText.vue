<template>
    <div class="form_cont">
        <input type="text"
        v-model="ValoreText" 
        >
        <a href="#"
        @click.prevent="$emit('ricerca',ValoreText)"
        >Search</a>
    </div>
</template>

<script>
export default {
    name: 'InputText',
    data(){
        return{
            ValoreText : ""
        }
    }
}
</script>

<style lang='scss' scoped>
@import "../../assets/style/vars.scss";
.form_cont{
    display: flex;
    align-items: center;
    gap: 10px;
    input{
        border: solid 0.5px white;
        font-weight: 100;
        background: $bg-head;
        color:white;
        height: 30px;
        padding-left: 3px;
    }
    a{
        text-decoration: none;
        color: #DC1A28;
        font-weight: 100;
        font-size: 16px;
        border: solid 1px #DC1A28;
        padding:5px;
        background:$bg-head;
    }
}
</style>