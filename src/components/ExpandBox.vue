<script setup>
import { computed, ref, defineProps } from 'vue'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  content: {
    type: String,
    default: 'Conteúdo da caixa de expansão'
  },
  qtde: {
    type: Number,
    default: 1
  },
  style: {
    type: Object,
    default: () => {}
  }
})

const showContent = ref(false)
const buttonText = computed(() => (showContent.value ? 'Esconder' : 'Mostrar'))
</script>

<template>
  <div>
    <button @click="showContent = !showContent">{{ buttonText }}</button>
    <div v-if="showContent" class="expand-box" :style="props.style">
      <h1>{{ props.title }}</h1>
      <p>{{ props.content }}</p>
      <p>Quantidade: {{ props.qtde }}</p>
    </div>
  </div>
</template>

<style scoped>
.expand-box {
  height: 100%;
  padding: 20px;
  border: 1px solid rgb(250, 0, 0);
  border-radius: 10px;
  box-shadow: 3px 3px 2px 2px gray;
}
</style>
