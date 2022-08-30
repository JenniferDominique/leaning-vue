/* eslint-disable */

<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Form para criar uma nova tarefa">
                <input type="text" class="input" placeholder="Nome da nova atividade" />
            </div>
            <div class="column">
                <Temporizador/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Temporizador from './Temporizador.vue'

export default defineComponent({
    name: 'Formulario',
    components: {
        Temporizador
    }
})
</script>