<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{task.description}}
            </div>
            <div class="column">
                <Cronometro :timeInSeconds="task.durationInSeconds"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import {defineComponent, PropType} from 'vue'
    import Cronometro from './Cronometro.vue'
    import ITarefa from '../interfaces/ITarefa'

    export default defineComponent({
        name: 'Tarefa',
        components: {
            Cronometro
        },
        props: {
            task: {
                type: Object as PropType<ITarefa>,
                required: true
            }
        }
    })
</script>

<!--scoped escopado esse estilo soh sera usado para esse componente-->
<style scoped> 
    .box {
        background: #FAF0CA
    }
</style>