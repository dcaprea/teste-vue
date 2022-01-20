<template>
    <div>
        <h2> TESTE REPETIÇÃO</h2>
        <ul>
            <li v-for="(item, index) in lista" :key="index">
                {{ item.nome +' '+ item.idade }}
            </li>
        </ul>
        <ul>
            <li v-for="item2 in ordenaLista" :key="item2.index">
                {{ item2 }}
            </li>
        </ul>
        <ul>
            <li v-for="item3 in ordenaIdade" :key="item3.index">
                {{ `Me nome é: ${item3.nome} e minha idade é: ${item3.idade}` }}
            </li>
        </ul>
        <h2>ADD TASK</h2>
        <input type="text" v-model="newTask" /> <button @click="handleAddTask">Adicionar Tarefa</button>
        <ul>
            <li v-for="tarefa in tarefas" :key="tarefa.index">
                {{ tarefa }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default{
        name: 'Repetition',
        data(){
            return{
                newTask: '',
                tarefas: [
                    'Tarefa 1',
                    'Tarefa 2',
                    'Tarefa 3'
                ],
                lista: [
                    {nome: 'Daniel', idade: 10},
                    {nome: 'Camila', idade: 46},
                    {nome: 'Vicente', idade: 80},
                    {nome: 'Bejamim', idade: 46},
                ],
                numbers: [
                    1,40,30,60,2,4,200, 35
                ]
            }
        },
        computed:{
            ordenaLista: function(){
                return this.numbers.filter( function(item) {
                    return item > 100
                })
            },
            ordenaIdade: function(){
                return this.lista.filter( function(item) {
                    return item.idade < 30
                })
            }
        },
        methods: {
            handleAddTask: function(){
                this.tarefas.push(this.newTask)
                this.newTask = ''
            }
        }
    }
</script>

<style>
</style>