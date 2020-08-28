<template>
    <div class="cont__title mb-5 pt-2 pb-2">
        <h1 :class="color">{{title}} <a :href="pagina" :target="target" >{{texto}}</a> </h1>
        <Subtitulo/>
    </div>
</template>

<script>
import Subtitulo from '@/components/Subtitulo.vue'
export default {
    name:'Titulo.vue',
    components:{
        Subtitulo
    },
    props:['title','color'],
    data(){
        return {
            pagina:'https://vuejs.org/',
            texto:'Vue JS',
            target:'_blank'
        }
    }
}
</script>

<style>
    body{
     background-color: #42b883;
    } 
    .cont__title{
        background-color: #35495e;
        border-radius: 10px;  
        color: white;      
    }
    a{
        color: #42b883;
    }
    a:hover{
        color: #42b883;
        border: 1px solid #42b883;
        box-sizing: border-box;
    }
    .btn-vue{
        background-color: #42b883;
        color: white;
    }
    .btn-vue:hover{
        background-color: #2ba16c;
        color: white;
    }
    .black{
        color: "white";
    }
    .cont__agen{
        width: 90%;
        margin: 0 auto;
    }
</style>

