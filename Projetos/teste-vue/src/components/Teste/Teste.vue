<template>
    <div id="componentBase">
      <div id="teste1" :class="{ backgroundRed: nomeCorreto }" class="backgroundAmarelo">
      Nome:
        {{nome}}
        <br />
        Valor:
        {{valor}}
        <br />
        Valor Mudado - Computed
        {{valorMudado}}
        <br />
        Valor Mudado Method
        {{valorMudadoMethod() }}
        <br /><br />
        <input type="text" v-model="valorInput" name="valor" />
        <button @click="changeValue">Alterar</button>
        <br /><br />
        <input type="text" v-model="nomeDois" name="nomeDois" />
      </div>
        <div class="estrutura2" :class="[fundoVermelho, textoBranco]">
          dfs fds sdfsd fsdf sdf s
        </div>
    </div>
</template>


<script>
import './Teste.style.scss'

export default {
  name: 'Teste',
  data() {
    return {
      fundoVermelho: "backgroundRed",
      textoBranco: "whiteText",
      nome: "Daniel Aprea",
      valor: 10,
      valorInput: 0,
      nomeCorreto: false,
      nomeDois: ""
    }
  },
  computed: {
    //Fica observando nos seus dados raiz reativos
    valorMudado: function(){
      //Cacheado até valor ser alterado
      return this.valor+2
    },
    now: function(){
      //Nunca será mudado porque não é um dado reativo
      return Date.now()
    }
  },
  watch: {
    valor: function(start, end){
      this.nome = start + " - - - - " + end
    },
    nomeDois: function(start){
      if(start=="Daniel"){
        this.nomeCorreto = true
      }else{
        this.nomeCorreto = false
      }
    }
  },
  methods: {
    valorMudadoMethod: function(){
      return this.valor+4
    },
    changeValue: function(){
      this.valor = this.valorInput
    }
  }
}
</script>
