<template>
    <ul class="info_film">
        <li>Titolo Originale: {{info.original_title}}</li>
        <li>Titolo: {{info.title}}</li>
        <li>Lingua: {{info.original_language}}</li>
        <li>Voto: {{info.vote_average}}</li>
    </ul>
</template>

<script>
export default {
    name:'InfoFilm',
    props:{
        info: Object
    }

}
</script>

<style lang='scss' scoped>

</style>