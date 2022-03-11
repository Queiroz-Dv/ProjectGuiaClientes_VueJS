<template>
  <div id="app">
    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h4>{{ index + 1}}</h4>
      <Cliente :cliente="cliente" />
      <hr>
      <h4> Edição: </h4>
      <input type="text" v-model="cliente.nome">
      <input type="text" v-model="cliente.email">
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
      Objcliente: {
        nome: "Eduardo Queiroz",
        email: "queiroz.dev@outlook.com",
        idade: 26,
      },
      Objcliente2: {
        nome: "Naylane Andrade",
        email: "nay@gmail.com",
        idade: 22,
      },
      Objcliente3: {
        nome: "Larissa Rocha",
        email: "lhara@gmail.com",
        idade: 24,
      },
      Objcliente4: {
        nome: "Patrícia Ribeiro",
        email: "patricia.ribeiro@gmail.com",
        idade: 28,
      },

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
        {
          id: 3,
          nome: " Daniela Silva",
          email: "dani@gmail.com",
          idade: 20,
        },
      ],
    };
  },
  components: {
    Cliente,
    //Produto
  },
};
</script>

<style scoped>
</style>
