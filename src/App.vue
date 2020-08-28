<template>
  <div id="app" class="container">    
    <Titulo :title="texto " color="black"/>
    <div class="cont__agen">
      <div class="text-left">
        <label for="titulo__edit">Edita el título</label>
        <input type="text" id="titulo__edit" placeholder="Escribe un Título" v-model="texto" class="form-control">
        <br>
        <button class="btn btn-vue " @click="alerta('Vue JS')">Ver Título</button>
    </div>
    <hr>
    <div class="row mt-3">
      <label for="titulo__edit" class="col-12">Agrega un tarea</label>
      <div class="col col-lg-4">
        <input type="text" placeholder="Título" v-model="titulo" class="form-control">
      </div>
      <div class="col col-lg-4">
        <input type="text" placeholder="Descripción" v-model="descrip" class="form-control" >
      </div>
      <div class="col col-lg-4">
        <button class="btn btn-vue btn-block" @click="agregar"> Agregar </button>
      </div>
    </div>
    <table class="table mt-2">
      <th>ID</th>
      <th>Título</th>
      <th>Descripción</th>
      <th>Eliminar</th>
      <tr v-for="(item, index) in hacer" :key="index">
        <td>{{index}}</td>
        <td>{{item.titulo}}</td>
        <td>{{item.descrip}}</td>
        <td> <button class="btn btn-danger" @click="eliminar(index)">Eliminar</button> </td>
      </tr>
    </table>    
    </div>
  </div>
</template>

<script>
import Titulo from './components/Titulo.vue'


export default {
  name: 'App',
  components: {
    Titulo
  },
  data() {
    return{
      texto: 'Agenda en ',
      titulo: '',
      descrip: '',
      hacer: [
        {titulo:'Ejemplo', descrip:'Descripción ejemplo'}
      ]
    }
  },
  methods: {
    alerta(msg){
      alert(this.texto + ' ' + msg)
    },
    agregar(){
      this.hacer.push({titulo: this.titulo, descrip: this.descrip})
    },
    eliminar(index){
      this.hacer.splice(index, 1)
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #35495e;
  margin-top: 50px;
  margin-bottom: 50px;
  background-color: rgba(255, 255, 255, 0.8);
  padding-bottom: 50px;
  padding-left: 0;
  padding-right: 0;
  border-radius: 10px;
}

</style>
