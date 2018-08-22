<template>
    <div>
        Introduce texto: <input v-model="texto" type="text" name="fname">
        <button :disabled="puedoCrear" @click="sentToParent()" type="button">Click Me!</button>
        <p v-show="puedoCrear">No puedes crear mas notas</p>
    </div>
</template>
<script>
export default {
    name:"Form",
    data:function(){
        return{
            texto:""
        }
    },
    methods:{
        sentToParent(){
             this.$emit('clicked', this.texto)
        }
    },
    props: ['puedoCrear'],
}
</script>

<style scoped>
   p {
    color:rgb(236, 15, 7);
}
</style>
