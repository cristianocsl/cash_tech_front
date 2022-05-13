<template>
<div>
  <table>
    <thead>
      <tr>
        <th>NOTA FISCAL</th>
        <th>SACADO</th>
        <th>CEDENTE</th>
        <th>EMISSÃO</th>
        <th>VALOR</th>
        <th>STATUS</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in info" v-bind:key="item.id">
        <td>{{ item.orderNfId }}</td>
        <td>{{ item.buyer.name }}</td>
        <td>{{ item.provider.name }}</td>
        <td>{{ item.emissionDate }}</td>
        <td>{{ item.value }}</td>
        <td>{{ item.orderStatusBuyer }}</td>
      </tr>
    </tbody>
  </table>

  <h1>Olá!</h1>
  <h1>Meu nome é {{ nome }}</h1>
  <ul v-for="item in array_de_nomes" v-bind:key="item">
    <li>{{ item }}</li>
  </ul>
</div>
</template>

<script>
import fetchData from '../services/data';

export default {
  data() {
    return {
      nome: 'Cristiano',
      array_de_nomes: ['Cristiano', 'José', 'Maria', 'João'],
      info: [],
    };
  },

  async mounted() {
    const { data } = await fetchData.list();
    console.log(data);
    this.info = data;
  },

  name: 'TableValue',
};
</script>
