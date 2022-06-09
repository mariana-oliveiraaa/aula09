<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_times: "",
      times: [
        { id: "d88574cd-fcf4-4074-a17a-925c042ffed9", name: "Time 1" },
        { id: "de3191c3-6eac-40db-9935-3a9ca9aa4edc", name: "Time 2" },
        { id: "23d04495-f56c-4466-96d3-74802b7770f9", name: "Time 3" },
        { id: "a54600e9-4aa4-4ec2-9c5a-78799a3f330c", name: "Time 4" },
      ],
    };
  },
  methods: {
    salvar() {
      const novo_id = uuid();
      this.times.push(  {
        id: novo_id,
        name: this.novo_time,
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ação</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.name }}</td>
            <td>?</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style></style>
