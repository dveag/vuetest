<template>
<div id="nota">
   <h1> Nota {{ident}}</h1>
   <div class="cuadrado">{{texto}}
        <img @click="deleteInstance()" src="../assets/borrar.png"  height="20" width="20">
   </div>

</div>
</template>

<script>

export default 
{
    name: 'Nota',
    components: 
    {
    
    },
    methods:
    {
        deleteInstance(){ 
            this.$emit('delete', this.ident)
      }
    },
    
    props: ['texto', 'ident'],
}
</script>
<style scoped>
   .cuadrado {
    width:5%;
    padding: 100px;
    background:rgb(221, 194, 76);
}
</style>
