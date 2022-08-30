<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <Cronometro :timeInSeconds='timeInSeconds' /> <!--O ':' quer dizer que esta lincado com o atributo(data) -->
        <Botao 
            @clicado="startTimer" 
            icone="fas fa-play" 
            texto="play" 
            :desabilitado="cronometroRodando" 
        />
        <Botao 
            @clicado="stopTimer" 
            icone="fas fa-stop" 
            texto="stop" 
            :desabilitado="!cronometroRodando" 
        />
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue'
    import Cronometro from './Cronometro.vue'
    import Botao from './Botao.vue'
    
    export default defineComponent({
        name: 'Temporizador',
        components: {
            Cronometro,
            Botao
        },
        emits: ['whenTimeStoped'],
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
                this.$emit('whenTimeStoped', this.timeInSeconds)
                this.timeInSeconds = 0
            }
        }
    })
    </script>