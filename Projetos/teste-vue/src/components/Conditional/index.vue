<template>
    <div>
        <h1>Renderização Condicional</h1>
        <button @click="interruptor">Interruptor</button>
        <template v-if="energia==true">Estou Ligado</template>
        <template v-else>Estou Desligado</template>
        <div>---------------------------------------------</div>
        <template v-if="energia">
            <p>Nome</p>
            <input type="text" key="input-nome" />
        </template>
        <template v-else>
            <p>E-mail</p>
            <input type="text" key="input-email" />
        </template>
        <div>---------------------------------------------</div>
        <div v-show="energia">
            <p>Nome</p>
            <input type="text" key="input-nome" />
        </div>
        <div v-show="energia==false">
            <p>E-mail</p>
            <input type="text" key="input-email" />
        </div>        
    </div>
</template>


<script>
export default{
    name: 'Conditional',
    data(){
        return{
            energia: false
        }
    },
    methods: {
        interruptor: function(){
            this.energia = !this.energia
        }
    }
}
</script>


<style>
</style>