<template>
    <div class="form_cont">
        <input type="text"
        v-model="ValoreText" 
        >
        <button
        @click.prevent="$emit('ricerca',ValoreText)"
        >Search</button>
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

</style>