<template>
<div>
  <h1>Olá!</h1>
  <h1>Meu nome é {{ nome }}</h1>
  <ul v-for="item in array_de_nomes" v-bind:key="item">
    <li>{{ item }}</li>
  </ul>
</div>
</template>

<script>

export default {
  name: 'TableValue',
  data() {
    return {
      nome: 'Cristiano',
      array_de_nomes: ['Cristiano', 'José', 'Maria', 'João'],
    };
  },
};
</script>
