<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <h4>Nome:{{ cliente.nome }}</h4>
    <hr />
    <p>Email: {{ cliente.email }}</p>
    <p v-if="showIdade === true">Idade: {{ cliente.idade }}</p>
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
