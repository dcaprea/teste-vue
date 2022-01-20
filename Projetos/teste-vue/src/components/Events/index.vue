<template>
    <div>
        <h2>EVENTOS</h2>
        <button v-on:click="acesso($event)">Clique aqui</button>
        <a  @click="teste1">Teste Sem Modificadores de Evento</a>
        <a v-on:click.prevent="teste1">Teste Com Modificadores de Evento</a>
    </div>
</template>

<script>
export default{
    name: 'Eventos',
    methods:{
        acesso: function(event){
            console.log(event.x)
        },
        teste1: function(){
            console.log("Ok");
        }
    }
}
</script>

<style></style>