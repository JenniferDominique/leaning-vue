<template>
    <Box>
        <div class="columns">
            <div class="column is-7">
                {{task.description || 'Tarefa sem descrição'}}
            </div>
            <div class="column">
                <Cronometro :timeInSeconds="task.durationInSeconds"/>
            </div>
        </div>
    </Box>
</template>

<script lang="ts">
    import {defineComponent, PropType} from 'vue'
    import Box from './Box.vue'
    import Cronometro from './Cronometro.vue'
    import ITarefa from '../interfaces/ITarefa'

    export default defineComponent({
        name: 'Tarefa',
        components: {
            Box,
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