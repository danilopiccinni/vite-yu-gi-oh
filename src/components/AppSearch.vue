<script>
import AppNameSearch from './AppNameSearch.vue'

import AppRandomDeck from './AppRandomDeck.vue'

import axios from "axios"

import {store} from "../store.js"


    export default {
        data() {
            return {
                store,
            }
        },

        components : {
            AppNameSearch,
            AppRandomDeck,
        },

        methods : {
            // metodo/funzione che viene richiamata al click del pulsante di scelta 
            creaMazzo(num) {

                this.store.isLoading = true
                
                this.store.nomeSearch = ''
                // tramite axios facciamo una richiesta API che ci restituisce un oggetto contenente il numero di carte richieste
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num='+num+'&offset=0').then((res) => {
                    
                    // assegnamo l'oggetto ricevuto tramite chiamata api 'store' che si trova nel 'store.js'
                    this.store.cards = res.data.data
                    
                    this.store.isLoading = false
                })


            },

            eseguiRicerca() {

                if (this.store.nomeSearch != '') {

                    this.store.isLoading = true
                    
                    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?&fname='+this.store.nomeSearch).then((res) => {
                                        
                        // assegnamo l'oggetto ricevuto tramite chiamata api 'store' che si trova nel 'store.js'
                        this.store.cards = res.data.data
                        this.store.numeroCarte = this.store.cards.length
                        
                        this.store.isLoading = false
                    }).catch((err) => {
                        alert(err.response.data)
                    })


                }
            }
        }
    }
               
</script>

<template>

    <AppRandomDeck @creaMazzo="creaMazzo(store.numeroCarte)"></AppRandomDeck>

    <AppNameSearch @eseguiRicerca="eseguiRicerca()"></AppNameSearch>

</template>

<style scoped lang="scss">


</style>