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
        <br><br>

        <label>Tecnologias</label><br>
        <span><input type="checkbox" value="JavaScript" v-model="tecnologias"/>JavaScript</span><br>
        
        <span><input type="checkbox" value="Css" v-model="tecnologias"/>Css</span><br>

        <span><input type="checkbox" value="VueJs" v-model="tecnologias"/>VueJs</span><br>

      </form>
    </div>
    <hr>
    <div class="item">
      <h2>Usuario Cadastrado</h2>

      <label>Nome: {{ user.nome }}</label><br>

      <label>Email: {{ user.email }}</label><br>

      <label>Qnt Func: {{ user.qtdFunc }}</label><br>

      <label>Opiniao: {{ opiniao }}</label><br>

      <label>Tecnologias: {{ tecnologias }}</label><br>

      <ul>
        <li v-for="tech in tecnologias" :key="tech">{{ tech }}</li>     
      </ul>

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
        tecnologias: []
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
