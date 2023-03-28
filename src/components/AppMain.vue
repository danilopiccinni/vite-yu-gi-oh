<script>

import {store} from "../store.js"

import axios from "axios"

import AppCard from './AppCard.vue';

export default {
    data() {
        return {

            numeroCarte: 0,
            store,
        }
    },

    components : {
        AppCard,
    },

    created() {

        // axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {

        //     this.store.cards = res.data.data

            
        // })
    },

    methods : {
        // metodo/funzione che viene richiamata al click del pulsante di scelta 
        creaMazzo(num) {

        // tramite axios facciamo una richiesta API che ci restituisce un oggetto contenente il numero di carte richieste
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num='+num+'&offset=0').then((res) => {

            // assegnamo l'oggetto ricevuto tramite chiamata api 'store' che si trova nel 'store.js'
            this.store.cards = res.data.data

            
        })
        }

    }
}
</script>

<template>
    <!-- contenitore dei vari bottoni per la scelta della quantità delle carte -->
    <div class="container-buttons">
        <button @click="numeroCarte=10 , creaMazzo(numeroCarte)">10 carte</button>
        <button @click="numeroCarte=15 , creaMazzo(numeroCarte)">15 carte</button>
        <button @click="numeroCarte=20 , creaMazzo(numeroCarte)">20 carte</button>
        <button @click="numeroCarte=25 , creaMazzo(numeroCarte)">25 carte</button>
        <button @click="numeroCarte=30 , creaMazzo(numeroCarte)">30 carte</button>
        <button @click="numeroCarte=35 , creaMazzo(numeroCarte)">35 carte</button>
        <button @click="numeroCarte=40 , creaMazzo(numeroCarte)">40 carte</button>
        <button @click="numeroCarte=45 , creaMazzo(numeroCarte)">45 carte</button>
        <button @click="numeroCarte=50 , creaMazzo(numeroCarte)">50 carte</button>
        <button @click="numeroCarte=55 , creaMazzo(numeroCarte)">55 carte</button>
        <button @click="numeroCarte=60 , creaMazzo(numeroCarte)">60 carte</button>
        <button @click="numeroCarte=65 , creaMazzo(numeroCarte)">65 carte</button>
        <button @click="numeroCarte=70 , creaMazzo(numeroCarte)">70 carte</button>
        <button @click="numeroCarte=75 , creaMazzo(numeroCarte)">75 carte</button>
        <button @click="numeroCarte=80 , creaMazzo(numeroCarte)">80 carte</button>
        <button @click="numeroCarte=85 , creaMazzo(numeroCarte)">85 carte</button>
        <button @click="numeroCarte=90 , creaMazzo(numeroCarte)">90 carte</button>
        <button @click="numeroCarte=95 , creaMazzo(numeroCarte)">95 carte</button>
        <button @click="numeroCarte=100 , creaMazzo(numeroCarte)">100 carte</button>
    </div>

    <!-- contenitore della scritta iniziale al caricamento della pagina -->
    <!-- con appunto il controllo che le carte siano 0 -->
    <div v-if="store.cards.length == 0" class="text">
        ^^^ scegli la quantità di carte qui sopra ^^^
    </div>

    <!-- ulteriore controllo che visualizza il loader mentre si aspetta la nuova generazione di carte -->
    <div v-else-if=" store.cards.length != numeroCarte" class="text">
        loading.....
    </div>
    
    <!-- ulteriore controllo che al raggiungimento delle carte richieste, quest'ultime vengono visualizzate -->
    <div v-else-if="store.cards.length == numeroCarte" class="container-cards">

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

    .container-buttons {
        display: flex;
        flex-wrap: nowrap;
        justify-content: center;
        gap: 5px;

        padding-top: 50px;
    }

    .text {
        color: red;
        font-size: 40px;
        font-weight: bold;
        padding-top: 20px;
        text-align: center;
    }
</style>