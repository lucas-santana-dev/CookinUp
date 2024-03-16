<script lang="ts">
import type { PropType } from 'vue';
import Tag from '@/components/Tag.vue'

export default {
    props: {
        ingrediente: { type: Array as PropType<string[]>, required: true }
    },
    components:{Tag}
}

</script>

<template>
    <section>
        <span class="subtitulo-lg sua-lista-texto">
            Sua lista:
        </span>
        <ul v-if="ingrediente.length" class="ingredientes-sua-lista">
            <li v-for="ingredientes in ingrediente" :key="ingredientes">
                <Tag :texto="ingredientes" ativa />
            </li>
        </ul>
        <p v-else class="paragrafo lista-vazia">
            <img src="../assets/images/icones/lista-vazia.svg" alt="">
            Sua lista está vasia, selecione ingredientes para iniciar
        </p>
    </section>
</template>
<style scoped>
.sua-lista-texto {
    color: var(--coral, #F0633C);
    display: block;
    text-align: center;
    margin-bottom: 1.5rem;
}


.lista-vazia {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 0.25rem;

    color: var(--coral, #F0633C);
    text-align: center;
}

.ingredientes-sua-lista {
    display: flex;
    justify-content: center;
    gap: 1rem 1.5rem;
    flex-wrap: wrap;
}
</style>