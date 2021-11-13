<template>
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
    props:["personagens"]
}
</script>