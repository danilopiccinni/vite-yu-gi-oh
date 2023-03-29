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



    <div class="container">
        <div class="titolo-crea">Crea il tuo mazzo a caso di:</div>
        <div class="container-buttons">
            <button @click="store.numeroCarte=10 , $emit('creaMazzo')">10 carte</button>
            <button @click="store.numeroCarte=15 , $emit('creaMazzo')">15 carte</button>
            <button @click="store.numeroCarte=20 , $emit('creaMazzo')">20 carte</button>
            <button @click="store.numeroCarte=25 , $emit('creaMazzo')">25 carte</button>
            <button @click="store.numeroCarte=30 , $emit('creaMazzo')">30 carte</button>
            <button @click="store.numeroCarte=35 , $emit('creaMazzo')">35 carte</button>
            <button @click="store.numeroCarte=40 , $emit('creaMazzo')">40 carte</button>
            <button @click="store.numeroCarte=45 , $emit('creaMazzo')">45 carte</button>
            <button @click="store.numeroCarte=50 , $emit('creaMazzo')">50 carte</button>
            <button @click="store.numeroCarte=55 , $emit('creaMazzo')">55 carte</button>
            <button @click="store.numeroCarte=60 , $emit('creaMazzo')">60 carte</button>
            <button @click="store.numeroCarte=65 , $emit('creaMazzo')">65 carte</button>
            <button @click="store.numeroCarte=70 , $emit('creaMazzo')">70 carte</button>
            <button @click="store.numeroCarte=75 , $emit('creaMazzo')">75 carte</button>
            <button @click="store.numeroCarte=80 , $emit('creaMazzo')">80 carte</button>
            <button @click="store.numeroCarte=85 , $emit('creaMazzo')">85 carte</button>
            <button @click="store.numeroCarte=90 , $emit('creaMazzo')">90 carte</button>
            <button @click="store.numeroCarte=95 , $emit('creaMazzo')">95 carte</button>
            <button @click="store.numeroCarte=100 , $emit('creaMazzo')">100 carte</button>

        </div>
    </div>

</template>

<style>

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;

    padding-top: 5px;
}

.titolo-crea {

}

.container-buttons {
        display: flex;
        flex-wrap: nowrap;
        justify-content: center;
        gap: 5px;
        padding-bottom: 5px;
        border-bottom: 5px solid grey;
    }


</style>