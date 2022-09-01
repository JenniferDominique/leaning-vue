<template>
    <div class="box has-text-weight-bold">
        <slot/> 
        <!--vai renderizar as informacoes que contem dentro dele em outro componente no caso aqui eh na Tarefa.vue-->
    </div>
</template>

<script lang="ts">
    import {defineComponent} from 'vue'

    export default defineComponent({
        name: 'Box'
    })
</script>

<!--scoped escopado esse estilo soh sera usado para esse componente-->
<style scoped> 
    .box {
        background: #FAF0CA
    }
</style>