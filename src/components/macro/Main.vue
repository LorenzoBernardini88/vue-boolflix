<template>
    <main>
        <div v-if="dataFilm ==0 && dataSerie ==0 " class="intro">
            <h1 class="jt --debug">
            <span class="jt__row">
                <span class="jt__text">BOOLFLIX</span>
            </span>
            <span class="jt__row jt__row--sibling" aria-hidden="true">
                <span class="jt__text">BOOLFLIX</span>
            </span>
            <span class="jt__row jt__row--sibling" aria-hidden="true">
                <span class="jt__text">BOOLFLIX</span>
            </span>
            <span class="jt__row jt__row--sibling" aria-hidden="true">
                <span class="jt__text">BOOLFLIX</span>
            </span>
            </h1>
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
.jt {
    position: relative;
    font-size: 20vmin;
    font-family: 'Staatliches', sans-serif;
    text-transform: uppercase;
    font-display: swap;
    text-shadow: 0 0 10px tomato;
}

.jt__row {
    display: block;
}
.jt__row:nth-child(1) {
    clip-path: polygon(-10% 75%, 110% 75%, 110% 110%, -10% 110%);
}
.jt__row:nth-child(2) {
    clip-path: polygon(-10% 50%, 110% 50%, 110% 75.3%, -10% 75.3%);
}
.jt__row:nth-child(3) {
    clip-path: polygon(-10% 25%, 110% 25%, 110% 50.3%, -10% 50.3%);
}
.jt__row:nth-child(4) {
    clip-path: polygon(-10% 0%, 110% 0%, 110% 25.3%, -10% 25.3%);
}

.jt__row.jt__row--sibling {
    position: absolute;
    top: 0;
    left: 0;
    user-select: none;
    witdh:800px;
}

.jt__text {
    display: block;
    transform-origin: bottom left;
    animation: moveIn 2s 0s cubic-bezier(.36,0,.06,1) alternate infinite;
}
.jt__row:nth-child(1) .jt__text {
    transform: translateY(-0.1em);
}
.jt__row:nth-child(2) .jt__text {
    transform: translateY(-0.3em) scaleY(1.1);
}
.jt__row:nth-child(3) .jt__text {
  transform: translateY(-0.5em) scaleY(1.2) ;
}
.jt__row:nth-child(4) .jt__text {
  transform: translateY(-0.7em) scaleY(1.3) ;
}
.jt__row:nth-child(5) .jt__text {
  transform: translateY(-0.9em) scaleY(1.4) ;
}
.jt__row:nth-child(6) .jt__text {
  transform: translateY(-1.1em) scaleY(1.5) ;
}

@keyframes moveIn {
  50%, 100% { 
    transform: translateY(0em);
    opacity: 1; 
    filter: blur(0px);
  }
  0%   { 
  opacity: 0; 
  filter: blur(10px);
  
  }
}

</style>