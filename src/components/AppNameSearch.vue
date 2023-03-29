<script>

import {store} from "../store.js"

 export default {
    data() {
        return {
            store,
        }
    }
 }
</script>

<template>

    <div class="container-ricerca">

        <span>Cerca per nome le tue card:</span>
        <input v-model="store.nomeSearch" @keyup.enter="$emit('eseguiRicerca')" type="text" placeholder="inserisci qui il nome" required>
        <button @click="$emit('eseguiRicerca')" >cerca</button>
        <span v-if="store.cards.length > 0"> Risultato ricerca: {{ store.cards.length }} card </span>
        
    </div>

</template>

<style>
    .container-ricerca {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 15px;

        padding-top: 25px;

    }

    input {
        width: 250px;
        text-align: center;
    }
</style>
