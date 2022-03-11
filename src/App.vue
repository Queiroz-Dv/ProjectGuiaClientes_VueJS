<template>
  <div id="app">
    <h3>Cadastro:</h3>
    <small id="nomeError" v-show="setError">Nome inválido tente novamente</small
    ><br />
    <input type="text" placeholder="nome" v-model="nomeField" /><br />
    <input type="email" placeholder="email" v-model="emailField" /><br />
    <input type="number" placeholder="idade" v-model="idadeField" /><br />
    <hr />
    <button @click="cadastrarUsuario">Cadastrar</button>
    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h4>{{ index + 1 }}</h4>
      <Cliente :cliente="cliente" @Delete="deletarUsuario($event)" />
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente.vue";
//import Produto from './components/Produto.vue';
export default {
  name: "App",
  data() {
    return {
      setError: false,
      nomeField: "",
      emailField: "",
      idadeField: 0,

      clientes: [
        {
          id: 1,
          nome: "Foster Smith",
          email: "foster.dev@outlook.com",
          idade: 36,
        },
        {
          id: 2,
          nome: "Helena Souza",
          email: "helena@gmail.com",
          idade: 27,
        },
      ],
    };
  },
  components: {
    Cliente,
    //Produto
  },
  methods: {
    cadastrarUsuario: function () {
      if (this.nomeField == "" || this.nomeField || this.nomeField.length < 3) {
        this.setError = true;
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now(),
        });
        this.nomeField = "";
        this.emailField = "";
        this.idadeField = 0;
        this.setError = false;
      }
    },

    deletarUsuario: function ($event) {
      var id = $event.idCliente;
      var newArray = this.clientes.filter((cliente) => cliente.id != id);
      this.clientes = newArray;
    },
  },
};
</script>

<style scoped>
#nomeError {
  color: red;
}
</style>
