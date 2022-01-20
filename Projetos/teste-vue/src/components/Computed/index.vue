<template>
    <div>
        <h1>{{changeTitle}}</h1>
        <p>Meus valores</p>
        <p>Saldo: {{saldo}}</p>
        <p>Devedor: {{devedor}}</p>
        <p>Total: <span :class="classObject">{{geraTotal}}</span></p> 
        <p>Total: <span :class="{ vermelho : geraTotal <0 }">{{geraTotal}}</span></p>
        <p>Total: <span :class="{ vermelho : verificaValor}">{{geraTotal}}</span></p> 
   
    </div>
</template>

<script>
    export default{
        name: 'Computed',
        data() {
            return{
                price: 123.45,
                title: 'Componente',
                saldo: 10000,
                devedor: 12000,
                total: 0,
            }
        },
        computed:{
            classObject: function () {
                return {
                'vermelho': this.verificaValor == true,
                'verde' : this.verificaValor == false
            }},
            changeTitle: function(){
                return this.title + " Computed"
            },
            geraTotal: function(){
                return this.saldo - this.devedor
            },
            verificaValor: function(){
                if(this.geraTotal < 0)
                    return true
                else
                    return false
            }
        }
    }
</script>

<style>
    .vermelho{
        color:#ff0000
    }
    .verde{
        color:#00ff00;
    }
</style>