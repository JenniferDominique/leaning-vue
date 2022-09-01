<template>
  <main class="columns is-gapless is-multiline">
    
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>

    <div class="column is-three-quarter">
      <Formulario @aoSalvarTarefa="salvarTarefa"/>
      
      <div class="lista">
        <Tarefa v-for="(task, index) in tasks" :key="index" :task="task"/>

        <Box v-if="taskListIsEmpty">
          Você não tem nenhuma tarefa ainda, bora criar uma? :D
        </Box>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'
import Box from './components/Box.vue'
import Formulario from './components/Formulario.vue'
import Tarefa from './components/Tarefa.vue'
import ITarefa from './interfaces/ITarefa'

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    Box,
    Formulario,
    Tarefa
  },
  data () {
    return {
      tasks: [] as ITarefa[]
    }
  },
  computed: {
    taskListIsEmpty () : Boolean {
      return this.tasks.length === 0
    }
  },
  methods: {
    salvarTarefa (task: ITarefa) {
      this.tasks.push(task)
    }
  }
});
</script>

<style>
  .lista {
    padding: 1.25rem
  }
</style>
