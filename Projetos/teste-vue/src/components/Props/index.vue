<template>
    <div>
        <h1>Componentes</h1>
        <InputTeste valor="Daniel" cor="vermelho" v-on:meutexto="recebeTexto" />
        <InputTeste  />
        <h3>AQUI VOU RETORNAR O FILHO</h3>
        {{ chuchu }}
    </div>
</template>

<script>
    import InputTeste from './input.vue'
    export default{
        components:{
            InputTeste
        },
        data(){
            return{
                chuchu: ''
            }
        },
        methods:{
            recebeTexto: function(valor){
                this.chuchu = valor
            }
        }
    }
</script>


<style></style>