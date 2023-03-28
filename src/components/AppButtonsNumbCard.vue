<script>
import axios from "axios"

import {store} from "../store.js"


    export default {
        data() {
            return {
                store,
            }
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
        },
    }
               
</script>

<template>

<div class="container-buttons">
        <button @click="store.numeroCarte=10 , creaMazzo(store.numeroCarte)">10 carte</button>
        <button @click="store.numeroCarte=15 , creaMazzo(store.numeroCarte)">15 carte</button>
        <button @click="store.numeroCarte=20 , creaMazzo(store.numeroCarte)">20 carte</button>
        <button @click="store.numeroCarte=25 , creaMazzo(store.numeroCarte)">25 carte</button>
        <button @click="store.numeroCarte=30 , creaMazzo(store.numeroCarte)">30 carte</button>
        <button @click="store.numeroCarte=35 , creaMazzo(store.numeroCarte)">35 carte</button>
        <button @click="store.numeroCarte=40 , creaMazzo(store.numeroCarte)">40 carte</button>
        <button @click="store.numeroCarte=45 , creaMazzo(store.numeroCarte)">45 carte</button>
        <button @click="store.numeroCarte=50 , creaMazzo(store.numeroCarte)">50 carte</button>
        <button @click="store.numeroCarte=55 , creaMazzo(store.numeroCarte)">55 carte</button>
        <button @click="store.numeroCarte=60 , creaMazzo(store.numeroCarte)">60 carte</button>
        <button @click="store.numeroCarte=65 , creaMazzo(store.numeroCarte)">65 carte</button>
        <button @click="store.numeroCarte=70 , creaMazzo(store.numeroCarte)">70 carte</button>
        <button @click="store.numeroCarte=75 , creaMazzo(store.numeroCarte)">75 carte</button>
        <button @click="store.numeroCarte=80 , creaMazzo(store.numeroCarte)">80 carte</button>
        <button @click="store.numeroCarte=85 , creaMazzo(store.numeroCarte)">85 carte</button>
        <button @click="store.numeroCarte=90 , creaMazzo(store.numeroCarte)">90 carte</button>
        <button @click="store.numeroCarte=95 , creaMazzo(store.numeroCarte)">95 carte</button>
        <button @click="store.numeroCarte=100 , creaMazzo(store.numeroCarte)">100 carte</button>
    </div>

</template>

<style scoped lang="scss">

.container-buttons {
        display: flex;
        flex-wrap: nowrap;
        justify-content: center;
        gap: 5px;

        padding-top: 50px;
    }

</style>