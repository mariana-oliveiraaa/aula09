<script>
import {v4 as uuid} from "uuid";
export default {
  data() {
    return {
     novo_jogador: "",
     novo_time: "",
     jogadores: [
        { id: "d88574cd-fcf4-4074-a17a-925c042ffed9", name: "Jogador 1", timesid:"1" , acoes:"???"},
        { id: "de3191c3-6eac-40db-9935-3a9ca9aa4edc", name: "Jogador 2", timesid:"1" , acoes:"???"},
        { id: "23d04495-f56c-4466-96d3-74802b7770f9", name: "Jogador 3", timesid:"2" , acoes:"???"},
        { id: "a54600e9-4aa4-4ec2-9c5a-78799a3f330c", name: "Jogador 4", timesid:"4" , acoes:"???"},
      ],
    };
  },
  methods: {
  salvar() {
      const novo_id = uuid();
      this.jogadores.push({
        id: novo_id,
        name: this.novo_jogador,
        acoes: this.novo_time,
        });
    },
  },
};
</script>
<template>
   <div class="container"> 
    <div class="title"> 
      <h2>Gerenciamento de Jogadores </h2>
    </div>
    <div class="form-input">
    <input type="text" v-model="novo_jogador" />
    <input type="text" v-model="novo_time" />
      <button @click="salvar"> Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
            <th>ID</th>
            <th>Nome</th>
            <th>Time ID</th>
            <th>Ação</th>
        </thead>
        <tbody>
          <tr v-for="jogador in jogadores" key="jogador.id">
          <td>{{jogador.id}}</td> 
          <td>{{jogador.name}}</td>
          <td>{{jogador.timesid}}</td>
           <td>{{jogador.acoes}}</td>
       </tr>
         
        </tbody>
      </table>
    </div>
  </div>
</template>
<style></style>
