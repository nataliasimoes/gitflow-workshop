<script setup>
import { defineEmits, ref } from "vue";
import Task from './Task.vue'

const emits = defineEmits(['finish'])

const defaultTask = ref(false)

const tasks = ref([
  {
    title: 'Listar Tarefas',
    description: 'Utilizar um v-for para listar tarefas',
    complete: false
  },
  {
    title: 'Marcar Tarefas como concluídas',
    description: 'Utilizar o evento de click para marcar tarefas como concluídas',
    complete: false
  },
  {
    title: 'Finalizar Tarefas',
    description: 'Finalizar tarefas e visualizar nota',
    complete: false
  }
])

const finished = ref(false)

function onClick() {
  emits('finish', [])
  finished.value = true
}

</script>

<template>
  <h1>RETRONATUS</h1>
  <Task v-model="defaultTask">
    <template #heading>Ler o código</template>

    Apenas leia o código.
  </Task>

  <Task v-model="tasks[0].complete">
    <template #heading>{{ tasks[0].title }}</template>

    {{tasks[0].description}}
  </Task>

  <br>
  <button :disabled="finished" @click="onClick">Finalizar Tarefa</button>
</template>

<style>
button {
  width: 172px;
  height: 48px;
  border: 1px solid black;
  background-color: #E83B2E;
  color: white;
  font-size: 16pt;
}

button:hover {
  cursor: pointer;
}

button:disabled {
  cursor: not-allowed;
  background-color: #e83a2e54;
}
</style>
