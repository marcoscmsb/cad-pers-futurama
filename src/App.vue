<template>
  <h1 class="text-6xl text-center mt-28 mb-20">{{ titulo }}</h1>
  <div class="grid grid-cols-12">
    <form
      class="
        w-full
        bg-gray-800
        rounded-lg
        sahdow-lg
        p-12
        justify-center
        items-center
        col-span-10 col-start-2
        sm:col-span-8 sm:col-start-3
        md:col-span-6 md:col-start-4
        grid grid-cols-1
        lg:grid-cols-2
        gap-2
      "
    >
      <input
        class="
          bg-transparent
          outline-none
          border-gray-700 border-2
          px-5
          py-2
          rounded
          focus:border-blue-500
          ease-in
          duration-200
          transition
          text-white
        "
        v-model="personagem.nome"
        type="text"
        placeholder="Digite o nome do personagem"
      />
      <input
        class="
          bg-transparent
          outline-none
          border-gray-700 border-2
          px-5
          py-2
          rounded
          focus:border-blue-500
          ease-in
          duration-200
          transition
          text-white
        "
        v-model="personagem.imagem"
        type="text"
        placeholder="Insera um link da imagem"
      />
      <button
        class="
          px-5
          py-2
          uppercase
          rounded
          border-gray-700 border-2
          text-white
          hover:bg-blue-500 hover:border-blue-500
          ease-in
          duration-200
          transition
          col-span-full
        "
        @click="adicionar"
        type="button"
      >
        Adicionar
      </button>
    </form>
  </div>
  <app-personagens-table :personagens="personagens"/>


</template>

<script>
import AppPersonagensTable from "./components/AppPersonagensTable.vue";

export default {
components: {
  AppPersonagensTable
},

  data() {
    return {
      titulo: "Cadastro Personagem Futurama",
      personagem: {},
      personagens: [],
    };
  },
  methods: {
    adicionar() {
      this.personagens.push(Object.assign({}, this.personagem));
      this.personagem = {};
    },
  },
};
</script>
