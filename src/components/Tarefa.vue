<template>
    <Box class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || 'Tarefa sem descrição' }}
            </div>
            <div class="column">
                <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </Box>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefa';
import Cronometro from './Cronometro.vue';
import Box from './Box.vue';
import { defineComponent, PropType } from 'vue';

export default defineComponent({
    name: 'Tarefa',
    components: { 
        Cronometro,
        Box
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>

<style scoped>
.box {
    background-color: #FAF0CA;
}
</style>