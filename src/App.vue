<script setup>

import ExpandBox from './components/ExpandBox.vue'

const caixas = [
  { id: 1, title: 'caixa 1' },
  { id: 2, title: 'caixa 2', qtde: 20, style: { backgroundColor: 'red' } },
  { id: 3, title: 'caixa 3', content: 'conteudo secreto da caixa 3' },
  { id: 4, title: 'caixa 4', content: 'conteudo da caixa', qtde: 5 }
]

 const titulo = 00
 </script>

<template>
  <div class="caixa1">
    <expand-box title="caixa 1" v-for="caixa in caixas" :key="caixa.id" v-bind="caixa" />
  </div>
</template>

<style scoped>
.caixa1 {
  padding: auto;
  margin-top: 25px;
  width: 290px;
}
</style>
