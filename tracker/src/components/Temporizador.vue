<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <Cronometro :timeInSeconds='timeInSeconds' /> <!--O ':' quer dizer que esta lincado com o atributo(data) -->
        <button 
            class="button" 
            @click="startTimer"
            :disabled="cronometroRodando"
        >
            <span class="icon">
                <i class="fas fa-play" />
            </span>
            <span>Play</span>
        </button>
        <button 
            class="button" 
            @click="stopTimer"
            :disabled="!cronometroRodando"
        >
            <span class="icon">
                <i class="fas fa-stop" />
            </span>
            <span>Pausa</span>
        </button>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'
    import Cronometro from './Cronometro.vue'
    
    export default defineComponent({
        name: 'Temporizador',
        components: {
            Cronometro
        },
        data() {
            return {
                timeInSeconds: 0,
                cronometro: 0,
                cronometroRodando: false
            }
        },
        methods: {
            startTimer() {
                this.cronometro = setInterval(() => { // Contar tempo de duração
                    this.timeInSeconds += 1
                }, 1000) // 1 second = 1000 milliseconds

                this.cronometroRodando = true
            },
            stopTimer() {
                clearInterval(this.cronometro)
                this.cronometroRodando = false
            }
        }
    })
    </script>