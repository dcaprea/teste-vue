<template>
    <div>
        <h1>Formulários</h1>
        <input type="text" v-model="input1" />
        {{ input1 }}
        <hr />
        <textarea v-model="textareanaofunciona"></textarea>
        <hr />
        <label>Daniel
        <input type="checkbox" value="Daniel" v-model="nomes" />
        </label>
        <label>Camila
        <input type="checkbox" value="Camila" v-model="nomes" />
        </label>
        <label>Vicente
        <input type="checkbox" value="Vicente" v-model="nomes" />
        </label>
        <label>Benjamim
        <input type="checkbox" value="Benjamim" v-model="nomes" />
        </label>                  
        {{ nomes }}

        {{ clickes }}

        <hr />

        <select v-model="itemSelecionado">
            <option :value="item" v-for="item in itensSelect" :key="item.index">{{ item.nome }}</option>
        </select>
        {{ `Você selecionou ${itemSelecionado.nome} de valor ${itemSelecionado.valor}` }}
    </div>
</template>

<script>
export default{
    data(){
        return{
            input1: '',
            textareanaofunciona: 'Não vai funcionar',
            nomes: [],
            clickes: 0,
            itensSelect:[
                {nome:"Daniel", valor:1},
                {nome:"Camila", valor:2},
                {nome:"Vicente", valor:3},                
                {nome:"Benjamim", valor:4},                 
            ],
            itemSelecionado: {nome: "Nada", valor:0}
        }
    },
    watch:{
        nomes: function(){
            this.clickes ++
        }
    }
}
</script>

<style></style>