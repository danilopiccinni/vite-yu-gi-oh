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

        <span v-if="store.cards.length > 0"> trovati : {{ store.cards.length }} card </span>
        <span>filtra per nome</span>
        <input v-model="store.nomeSearch" @keyup.enter="$emit('eseguiRicerca')" type="text" placeholder="inserisci qui il nome" required>
        <button @click="$emit('eseguiRicerca')" >cerca</button>

    </div>

</template>

<style>
    .container-ricerca {
        display: flex;
        justify-content: center;
        gap: 15px;

        padding-top: 25px;

        input {
            width: 250px;
        }
    }
</style>
