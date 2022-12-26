<template>
  <div id="app">
    <h1>Fazer Cadastro</h1>

    <div>
      <form>
        <label>Nome: </label>
        <input type="text" v-model="user.nome">
        <br>

        <label>Email: </label>
        <input type="text" v-model="user.email">
        <br>

        <label>Qnt Func: </label>
        <input type="text" v-model="user.qtdFunc">
        <br>

        <label>Opniao: </label>
        <textarea v-model="opiniao"></textarea>
        <br><br><hr>

        <label>Tecnologias</label><br>
        <span><input type="checkbox" value="JavaScript" v-model="tecnologias"/>JavaScript</span><br>
        
        <span><input type="checkbox" value="Css" v-model="tecnologias"/>Css</span><br>

        <span><input type="checkbox" value="VueJs" v-model="tecnologias"/>VueJs</span><br>

      </form>
      <br><hr><br>

      <label>Qual o tipo de contratação</label>
      <select v-model="tipoSelecionado">
        <option v-for="item in tipos" :key="item.id" value="item.nome">{{ item.nome }}</option>        
      </select><br><br>

      
    </div><br><hr><br>

    <label>Qual seu nivel?</label>
    <span><input type="radio" value="basico" v-model="nivel"/>Básico</span>
    <span><input type="radio" value="intermediario" v-model="nivel"/>Intermediário</span>
    <span><input type="radio" value="avancado" v-model="nivel"/>Avançado</span>
    <br>
    

    <hr><br>

    <button @click.prevent="enviar">Enviar</button>

    <br><hr>
    <div class="item" v-show="resultado">
      <h2>Usuario Cadastrado</h2>

      <label>Nome: {{ user.nome }}</label><br>

      <label>Email: {{ user.email }}</label><br>

      <label>Qnt Func: {{ user.qtdFunc }}</label><br>

      <label>Opiniao: {{ opiniao }}</label><br>

      <label>Tecnologias: {{ tecnologias }}</label><br>
      

      <ul>
        <li v-for="tech in tecnologias" :key="tech">{{ tech }}</li>     
      </ul><br>

      <label>Tipo de Contratação: {{ tipoSelecionado }}</label><br>

      <label>Nível atual: {{ nivel }}</label>

      
    </div>
  </div>

</template>

<script>
  export default {
    name: 'App',
    data(){
      return{
        user:{
          nome: '',
          email: '',
          qtdFunc: 0
        },
        opiniao: '',
        tecnologias: [],
        tipos: [
          {id: 1, nome: 'Freelancer'},
          {id: 2, nome: 'CLT'},
          {id: 3, nome: 'PJ'}
        ],
        tipoSelecionado: 'Freelancer',
        nivel: 'basico',
        resultado: false
      }
    },
    methods: {
      enviar(){
        this.resultado = true;
      }
    }
  }

</script>

<style>
label{
  display: flex;
  flex-direction: column;
}


</style>
