<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      categorias: [
        { id: "07a99871-0b57-4ecb-9286-12eedbea2c0d", nome: "ficção" },
        { id: "8f3a4fec-9959-4505-979e-294a57733da5", nome: "ação" },
        { id: "62bb5503-9197-4e14-9338-9e2ed9ed21dd", nome: "aventura" },
      ],
      nova_categoria: "",
    };
  },
  methods: {
    salvar() {
      if (this.nova_categoria !== "") {
        const novo_id = uuidv4();
        this.categorias.push({
          id: novo_id,
          nome: this.nova_categoria,
        });
        this.nova_categoria = "";
      }
    },
    excluir(categoria) {
      const indice = this.categorias.indexOf(categoria);
      this.categorias.splice(indice, 1);
    },
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="title">
        <h2>Categorias</h2>
      </div>
      <div class="form-input">
        <input type="text" placeholder="Categoria" v-model="nova_categoria" />
        <button @click="salvar">Salvar</button>
      </div>
      <div class="list-cat">
        <table>
          <thead>
            <tr>
              <th>ID</th>
              <th>Categoria</th>
              <th>Excluir</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="categoria in categorias" :key="categoria.id">
              <td>{{ categoria.id }}</td>
              <td>{{ categoria.nome }}</td>
              <button @click="excluir(categoria)">Excluir</button>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </main>
</template>

<style></style>
