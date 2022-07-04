<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      livros: [
        {
          id: "0f816a46-00dc-4286-ab19-54e8ba0611b7",
          livro: "Livros1",
          categoria: "Ficção",
        },
        {
          id: "f1fb411d-1671-4c60-a0d2-d3b521dedc85",
          livro: "Livros2",
          categoria: "Ação",
        },
        {
          id: "beef9eee-d5c7-4a8d-8f40-b3a55419f9b6",
          livro: "Livros3",
          categoria: "Aventura",
        },
      ],
      novo_livro: "",
      nova_categoria: "",
    };
  },
  methods: {
    salvar() {
      if ((this.novo_livro, this.nova_categoria !== "")) {
        const novo_id = uuidv4();
        this.livros.push({
          id: novo_id,
          livro: this.novo_livro,
          categoria: this.nova_categoria,
        });
        this.novo_livro = "";
        this.nova_categoria = "";
      }
    },
    excluir(livro) {
      const indice = this.livros.indexOf(livro);
      this.livros.splice(indice, 1);
    },
  },
};
</script>

<template>
  <main>
    <div class="container">
      <div class="form-input">
        <input type="text" placeholder="Livro" v-model="novo_livro" />
        <select type="text" v-model="nova_categoria">
          <option value="" disabled>Categoria</option>
          <option value="ficção">ficção</option>
          <option value="ação">ação</option>
          <option value="aventura">aventura</option>
        </select>
        <button @click="salvar">Salvar</button>
      </div>
      <div class="list-liv">
        <table>
          <thead>
            <tr>
              <th>ID</th>
              <th>Livros</th>
              <th>Categoria</th>
              <th>Excluir</th>
            </tr>
          </thead>

          <tbody>
            <tr v-for="livro in livros" :key="livro.id">
              <td>{{ livro.id }}</td>
              <td>{{ livro.livro }}</td>
              <td>{{ livro.categoria }}</td>
              <button @click="excluir(livro)">Excluir</button>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </main>
</template>

<style></style>
