<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                Nome da tarefa
            </div>
            <div class="column">
                <Cronometro :timeInSeconds="15"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import {defineComponent} from 'vue'
    import Cronometro from './Cronometro.vue'

    export default defineComponent({
        name: 'Tarefa',
        components: {
            Cronometro
        }
    })
</script>

<!--scoped escopado esse estilo soh sera usado para esse componente-->
<style scoped> 
    .box {
        background: #FAF0CA
    }
</style>