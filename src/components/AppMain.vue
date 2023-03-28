<script>
import {store} from "../store.js"

import axios from "axios"

import AppCard from './AppCard.vue';

export default {
    data() {
        return {
            store,
        }
    },

    components : {
        AppCard,
    },

    created() {

        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {

            this.store.cards = res.data.data
            
        })
    }
}
</script>

<template>

    <div class="container-cards">

        <AppCard v-for="card in store.cards" :card="card"></AppCard>

    </div>

</template>

<style scoped lang="scss">

    .container-cards {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
    }
</style>