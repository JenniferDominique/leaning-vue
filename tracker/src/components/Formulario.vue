/* eslint-disable */

<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Form para criar uma nova tarefa">
                <input type="text" class="input" placeholder="Nome da nova atividade" />
            </div>
            <div class="column">
                    <div class="is-flex is-align-items-center is-justify-content-space-between">
                        <section>
                            <strong>00:00:00</strong>
                        </section>
                        <button class="button">
                            <span class="icon">
                                <i class="fas fa-play" />
                            </span>
                            <span>Play</span>
                        </button>
                        <button class="button">
                            <span class="icon">
                                <i class="fas fa-stop" />
                            </span>
                            <span>Stop</span>
                        </button>
                    </div>
                </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'FormularioTarefa'
})
</script>