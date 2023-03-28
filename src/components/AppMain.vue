<script>
import AppButtonsNumbCard from "./AppButtonsNumbCard.vue";

import {store} from "../store.js"

import AppCard from './AppCard.vue';

export default {
    data() {
        return {
            store,
        }
    },

    components : {
        AppCard,
        AppButtonsNumbCard
    },
}
</script>

<template>

    <AppButtonsNumbCard></AppButtonsNumbCard>

    <!-- contenitore della scritta iniziale al caricamento della pagina -->
    <!-- con appunto il controllo che le carte siano 0 -->
    <div v-if="store.numeroCarte == null" class="text">
        ^^^ scegli la quantità di carte qui sopra ^^^
    </div>

    <!-- ulteriore controllo che visualizza il loader mentre si aspetta la nuova generazione di carte -->
    <div v-else-if="store.cards.length != store.numeroCarte" class="text">
        loading.....
    </div>
    
    <!-- ulteriore controllo che al raggiungimento delle carte richieste, quest'ultime vengono visualizzate -->
    <div v-else-if="store.cards.length == store.numeroCarte" class="container-cards">

        <!-- ciclo v-for per la visualizazzione delle carte richieste -->
        <AppCard v-for="card in store.cards" :card="card"></AppCard>

    </div>


</template>

<style scoped lang="scss">

    .container-cards {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;

        max-width: 80%;
        margin: 50px auto;
    }

    .text {
        color: red;
        font-size: 40px;
        font-weight: bold;
        padding-top: 20px;
        text-align: center;
    }
</style>