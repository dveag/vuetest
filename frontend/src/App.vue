<template>
  <div id="app">
    <formulario @clicked="receivedFromChild" :puedoCrear="checkNotes"></formulario>
    <Nota @delete="borraDeArray" :key="id" v-for="(texto,id) in arrayTextos" :texto="texto" :ident="id"> </Nota>
  </div>
</template>

<script>
import Form from './components/Form.vue'
import Nota from './components/Nota.vue'

export default {
  name: 'app',
  components: {
    'formulario':Form,
    Nota
  },
    methods:{
      receivedFromChild(texto){ 
         this.arrayTextos.push(texto)
      },
      borraDeArray(id){ 
        this.arrayTextos.splice(id, 1);
      },
  },
  computed:
    {
        checkNotes(){
          return this.arrayTextos.length >= 5
        }

    },
  data:function(){
        return{
            arrayTextos:[]
        }
    },
}
</script>

<style>

</style>
