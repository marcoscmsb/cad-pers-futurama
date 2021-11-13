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

  <table class="table text-gray-400 border-separate space-y-6 text-sm w-full">
    <thead class="bg-gray-800 text-gray-500">
      <th class="p-3">nome</th>
      <th class="p-3">imagem</th>
    </thead>
    <tbody>
      <tr
        class="bg-gray-800"
        v-for="personagem in personagens"
        :key="personagem.nome"
      >
        <td class="p-3">{{ personagem.nome }}</td>
        <td class="p-3">
          <img
            class="object-scale-down h-48 w-full "
            :src="personagem.imagem"
            alt="Imagem do Personagem"
          />
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
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
