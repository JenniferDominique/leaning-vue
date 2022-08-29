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
                            <strong>
                                {{ timePassad }}
                            </strong>
                        </section>
                        <button class="button" @click="startTimer">
                            <span class="icon">
                                <i class="fas fa-play" />
                            </span>
                            <span>Play</span>
                        </button>
                        <button class="button" @click="stopTimer">
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
    name: 'FormularioTarefa',
    data () {
        return {
            timeInSeconds: 0
        }
    },
    computed: {
        timePassad () : string {
            return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8)
        }
    },
    methods: {
        startTimer () {
            setInterval(() => { // Contar tempo de duração
                this.timeInSeconds += 1
            }, 1000) // 1 second = 1000 milliseconds
            console.log("Inciando o timer")
        },
        stopTimer () {
            console.log("Parando o timer")
        }
    }
})
</script>