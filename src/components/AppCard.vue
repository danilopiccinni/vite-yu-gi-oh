<script>
import { store } from '../store';

export default {
    data() { 
        return {
            store,
        }
    },

    props : {
        card: Object,
    }
}
</script>

<template>

    <div class="card">

        <div class="container-image-card">
            <img class="image-card" :src="card.card_images[0].image_url" alt="'image-card' + {{ card.name }}">
        </div>

        <div class="info-card">
            <div class="contanier-name-card">
                <em class="id-info">Name:</em> <strong class="value name"> {{card.name}}</strong>
            </div>
            <div class="container-type-card">
                <em class="id-info">Type:</em> <strong class="value type"> {{card.type}}</strong>
            </div>
            <div class="container-race-card">
                <em class="id-info">Race:</em> <strong class="value race"> {{card.race}}</strong>
            </div>
        </div>
    </div>

</template>

<style scoped lang="scss">


    .card {
        width: calc(100% / 5 - 20px / 5 * 4);

        display: flex;
        flex-direction: column;

        img {
            width: 100%;
        }

        .id-info {
            font-size: 10px;
        }

        .value {
            font-size: 15px;
        }
    }

</style>