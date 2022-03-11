<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <h4>Nome:{{ cliente.nome }}</h4>
    <hr />
    <p>Email: {{ cliente.email }}</p>
    <p v-if="showIdade === false">Idade: {{ cliente.idade }}</p>
    <button @click="mudarCor($event)">Mude a cor!</button>
    <button @click="deleteEvent">Deletar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false,
    };
  },

  props: {
    cliente: Object,
    showIdade: Boolean,
  },

  methods: {
    mudarCor: function ($event) {
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    deleteEvent: function () {
      console.log("Emitindo evento filho");
      this.$emit("Delete");
    },
  },
};
</script>

<style scoped>
.cliente {
  background-color: gainsboro;
  max-width: 500px;
  height: 200;
  padding: 1%;
  margin-top: 2%;
}

.cliente-premium {
  background-color: darkkhaki;
  color: whitesmoke;
  max-width: 500px;
  height: 200;
  padding: 1%;
  margin-top: 2%;
}
</style>
